# ATLAS Ocean Lidar Scientific Dataset

Processed scientific data supporting an ICESat-2/ATLAS ocean lidar attenuation study.

## Coverage
- Months: January, April, August and October 2019
- Regions: NA, WP, EP, IN (IO), NS, ECS and LP (RDP)
- Aggregation scales: 4, 20 and 40 km
- Total derived aggregated profiles: 3,304,486

## Directories
- D01_Foundation: sample statistics, SPP, telemetry and instrument response
- D02_ATLAS_MODIS: profile-level lidar estimates and matched ocean-color data
- D03_Analysis: signal diagnostics, sample selection and fitting-depth evaluation
- D04_Poisson_Simulation: controlled exponential-Poisson numerical results

Each folder contains a separate README.md explaining its data files.

## Data formats
- HDF5: named numerical arrays for individual aggregated profiles
- Excel: named worksheets grouped by scientific subject
- file_manifest.csv: relative file paths and sizes

## Source data
NASA ICESat-2 ATL03 and MODIS-Aqua monthly Level-3 ocean-color products.
The files contain processed and derived results, not the original NASA input data.

## Limitations
These files permit reuse and verification of the reported derived scientific results.
They do not contain the complete raw-photon processing chain or every intermediate case.

## Citation and license
The associated manuscript has not yet been published. The article citation and dataset DOI will be added when available. No data reuse license has been assigned at this stage.
