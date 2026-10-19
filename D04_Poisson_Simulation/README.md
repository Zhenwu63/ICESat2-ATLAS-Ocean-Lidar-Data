# D04 — Controlled Exponential-Poisson Simulation

## poisson_simulation.xlsx
- parameters: simulation constants and configuration
- anchor_summary: observed-data-derived N0 and background percentiles
- standard_5bin: results using the standard 5-bin smoothing
- smoothing_sensitivity: simulated attenuation and R2 by smoothing window
- R2_pass_rates: selection passing fractions versus K0 and threshold
- fitting_depth_axis: corrected fitting-depth coordinates

## Model
Observed counts at depth x are modeled as:

    Y(x) ~ Poisson[N0 * exp(-2*K0*x) + B]

After sampling, the known background B is subtracted.
Positive smoothed bins are used in a log-linear fit.

## Numerical settings
- Fitting window: 5–15 m apparent depth
- Smoothing windows: 1, 3, 5, 7, 9, 11, 13 and 15 bins
- Standard smoothing: 5 bins
- Repetitions per K0: 10000
- Random seed, N0, B and K0 range are included in the parameters worksheet
- Simplified model excludes IRF convolution and deconvolution

Passing rates use valid positive attenuation estimates as the denominator.
Results are statistical aggregates; individual Poisson draws are not stored.
