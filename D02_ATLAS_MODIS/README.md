# D02 — ATLAS–MODIS Profile-Level Data

## Organization
Twenty-eight HDF5 files: one for each region and month.
Each file contains three scale-specific groups: /004km, /020km and /040km.

Example: EP_201904.h5

## Variables within each group
- profile_index: original 1-based row index in the corresponding derived source file
- latitude, longitude: profile coordinates, degrees
- SPP: surface-peak photon counts per emitted pulse
- laser_pulses: aggregated pulse count
- background_1ns: estimated background per 1 ns depth bin
- telemetry_valid_flag: telemetry quality indicator
- telemetry_surface_fraction: surface containment fraction
- z_tlm_min_m: minimum telemetry coverage depth, m
- z_tlm_p10_m: 10th percentile telemetry coverage depth, m
- Kd_531: MODIS-derived downward irradiance attenuation at 531 nm, m^-1
- chlor_a: MODIS chlorophyll-a, mg m^-3
- bb_531: MODIS bb at 531 nm, m^-1
- K_lidar: profile-by-zmin attenuation estimates, m^-1
- R2: profile-by-zmin fitting coefficients of determination
- zmin_apparent_m: the 11 fitting start depths

## Lidar processing
- zmin apparent depth: 0 to 5 m in 0.5 m intervals
- zmax apparent depth: fixed at 15 m
- Background subtraction, IRF deconvolution and refraction correction enabled
- Refractive index: 1.34
- Moving average: 5 depth bins
- Minimum positive fitting bins: 8
- No SPP or R2 sample filter applied during export
- Invalid values and MODIS nonmatches are represented by NaN

## Window columns
The columns of K_lidar and R2 correspond to zmin_apparent_m.
The 11th column corresponds to the 5–15 m fitting window.

## MODIS matching
The available positive MODIS pixels corresponding to the constituent
500 m subprofiles were averaged for each aggregated lidar profile.
K_d(531) was derived from MODIS-Aqua monthly Rrs using QAA_v6 and
the Lee et al. (2013) formulation with solar zenith angle 0 degrees.

## MATLAB example
```matlab
f = 'EP_201904.h5';
K = h5read(f,'/040km/K_lidar');
R2 = h5read(f,'/040km/R2');
Kd = h5read(f,'/040km/Kd_531');
zmin = h5read(f,'/040km/zmin_apparent_m');
```

## Python example
```python
import h5py
import numpy as np
with h5py.File('EP_201904.h5', 'r') as f:
    g = f['040km']
    K = np.asarray(g['K_lidar'])
    R2 = np.asarray(g['R2'])
    Kd = np.asarray(g['Kd_531']).ravel()
    zmin = np.asarray(g['zmin_apparent_m']).ravel()
    if K.shape[0] == len(zmin):
        K, R2 = K.T, R2.T
    print(K.shape, R2.shape, Kd.shape)
```

MATLAB and Python may display HDF5 dimensions in reversed order.
The full 264-case internal processing matrices are not distributed.
