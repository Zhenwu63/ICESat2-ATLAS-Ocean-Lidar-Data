# D01 — Foundation and Instrument Response

## sample_statistics.xlsx
- region_month_counts: profile counts grouped by region and month
- telemetry_global: depth-coverage fractions by aggregation scale
- telemetry_by_region: telemetry coverage by month, region and scale
- SPP_500m_distribution: 500 m surface-peak photon-count histogram
- SPP_500m_summary: 500 m SPP distribution statistics
- IRF_source_granules: desert ATL03 granules used for response estimation
- matched_profiles: derived profile numbers by region, month and scale

## instrument_response.xlsx
- land_IRF: background-subtracted land return against apparent depth
- processing_IRF: normalized response and causal deconvolution kernel

## Units and definitions
- SPP: detected surface-peak photons per emitted laser pulse
- IRF: instrument response function
- Depth: m; telemetry coverage fractions: dimensionless
- Land IRF is derived from separate July 2019 desert observations

No original ATL03 photon records are redistributed.
