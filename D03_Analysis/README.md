# D03 — Scientific Analysis

## signal_diagnostics.xlsx
- SPP_K_distribution: attenuation distributions at different aggregation scales
- SPP_K_composition: attenuation composition across SPP intervals
- IRF_summary: weighted diagnostic summary of response-related effects
- IRF_profile_diagnostics: selected real-profile processing comparisons
- IRF_example_profile: representative smoothed profiles before and after deconvolution
- IRF_example_info: metadata for the representative profile

## quality_and_validation.xlsx
- R2_overall: selection retention and attenuation statistics
- R2_by_SPP: selection retention by SPP
- K_distribution_R2: attenuation distributions by R2 threshold
- R2_by_Kd: selection retention across Kd intervals
- R2_retention_range: between-bin differences in retention
- R2_allowed_threshold: accepted R2 thresholds by scale and zmin
- processing_global: global scale and fitting-start sensitivity
- processing_by_region: corresponding region-specific results
- candidate_performance: the 53 admissible processing and screening combinations
- reference_by_Kd: 40 km, 5–15 m, R2>=0.5 reference statistics

## fitting_depth_analysis.xlsx
- end_depth_sensitivity: common-sample median attenuation against fitting end depth
- joint_window_grid: paired candidate/reference metrics across six Kd groups
- pareto_windows: non-dominated fitting-window combinations
- pareto_summary: summaries of Pareto windows
- noninferior_summary: regions of jointly non-inferior windows

## Reference and metrics
- Reference: 40 km aggregation, 5–15 m apparent-depth fitting, R2>=0.5
- Kd>=0.05 m^-1 for the main validation analysis
- RMSE and Bias: m^-1; MAPD and retention: percent
- Pearson_R: correlation coefficient
- All means no R2 threshold is imposed

## Joint fitting-window evaluation
- zmin: 0:0.5:5 m; zmax: 2:0.5:20 m
- Minimum fitting-window width: 2 m
- Candidate and 5–15 m reference metrics use the same valid paired profiles
- Telemetry P10 support depth must reach max(candidate zmax,15 m)
- Pareto selection uses changes in RMSE, absolute Bias and MAPD

Internal MATLAB script names are not used as public worksheet names.
