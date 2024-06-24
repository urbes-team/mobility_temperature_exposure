# mobility_temperature_exposure

This repository contains core code associated with the paper:

Lin, G. et al. Human mobility modulates temperature exposure in European cities

## Data required

Please note that to run the analysis scripts, additional data need to be downloaded from their respective sources as listed below:

- UrbClim temperature and mask data from Copernicus Climate Change Service (https://doi.org/10.24381/cds.c6459d3a)
- Temperature-mortality relationships (ERF) and minimum mortality temperatures (MMT) from Masselot et al. 2023 (https://doi.org/10.5281/zenodo.7672108) and Haung et al. 2023
- Daytime/nighttime population from Copernicus Climate Change Service (detailed in E Silva et al. 2020) 

Data generated from the study can be found on Zenodo at 10.5281/zenodo.12515269.

## Code organisation

Code in this repository is grouped as described below and are currently designed to be modified and executed individually as needed. Scripts in subsequent groups may be dependent on outputs from a script in the previous group, though the data outputs on Zenodo as specified above (https://doi.org/10.5281/zenodo.12515269) can also be used in place of certain processing steps. Unless otherwise noted, the scripts within each group are not dependent on each other.
- Files starting with "`00`" are pre-processing scripts. Please note that the bash script `000_prep_data_urbclim.sh` would need to run first to prepare the UrbClim temperature data.
- Files starting with "`01`" are attribution scripts applying the exposure-response relationships to the temperature data. Two scripts are provided:
  - `01_attribute.R` is for the best estimate exposure-response relationships and outputs timeseries of spatial maps
  - `01_attribute_simulations.R` is for the Monte Carlo simulated ensemble and outputs only the timeseries of difference between urban and rural averages
  - Attribution outputs are in attributable fraction.
- Files starting with "`02`" are core analysis scripts, translating attributable fractions into attributable deaths, aggregating across age groups, and performing spatial-temporal analyses.
  - The "base analysis" scripts (`02_base_analysis.py` and `02_base_analysis_simulated.py`) perform aggregations mostly on the temporal dimension, leaving the spatial dimension in the output (if present in the input).
  - The "timeseries" scripts (`02_urbanrural_avg_timeseries.py` and `02-2_timeseries_temporal_analysis.py`) are spatially aggregated into urban and rural averages, as well as the difference between the two. Note that `02-2_timeseries_temporal_analysis.py` is dependent on the outputs of `02_urbanrural_avg_timeseries.py`.
- Files starting with "`03`" are additional analysis scripts, providing outputs quoted in the paper. Supplementary tables S4-S11, listing the risks for each city, are outputs of `03_confidence_interval.py`.
- Files starting with "`Fig`" are used to produce the figures in the main text of the paper, along with any additional associated analyses.

## References

References: 

De Ridder, K., Lauwaet, D., and Maiheu, B., (2015): UrbClim – A fast urban boundary layer climate model. *Urban Climate*, 12, 21–48. https://doi.org/10.1016/J.UCLIM.2015.01.001.

E Silva, B. et al. (2020). Uncovering temporal changes in Europe’s population density patterns using a data fusion approach. *Nature communications*, 11(1), 4631. https://doi.org/10.1038/s41467-020-18344-5

Hooyberghs, H., Berckmans, J., Lauwaet, D., Lefebre, F., and De Ridder, K., (2019): Climate variables for cities in Europe from 2008 to 2017. *Copernicus Climate Change Service (C3S) Climate Data Store (CDS)*. https://doi.org/10.24381/cds.c6459d3a.

Huang, W.T.K. et al. Economic valuation of temperature-related mortality attributed to urban heat islands in European cities. *Nature Communications* 14, 7438 (2023). https://doi.org/10.1038/s41467-023-43135-z

Masselot et al. (2023): Excess mortality attributed to heat and cold: a health impact assessment study in 854 cities in Europe, *The Lancet Planetary Health*, https://doi.org/10.1016/S2542-5196(23)00023-2. 
