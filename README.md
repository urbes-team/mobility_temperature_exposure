# mobility_temperature_exposure

This repository contains core code associated with the paper:

Lin, G. et al. Daily and seasonal human mobility modulates temperature exposure in European cities

## Data required

Please note that to run the analysis scripts, additional data need to be downloaded from Zenodo repository of this project: 10.5281/zenodo.12515269.

The files on Zenodo was processed from the original data sources below:
### Temperature
- UrbClim temperature and mask data from Copernicus Climate Change Service (https://doi.org/10.24381/cds.c6459d3a)
### ERF and MMT 
- Temperature-mortality relationships (ERF) and minimum mortality temperatures (MMT) from Masselot et al. 2023 (https://doi.org/10.5281/zenodo.7672108) and Haung et al. 2023
### Population
- Daytime/nighttime population from European Commission’s Joint Research Centre Data Catalog (https://data.jrc.ec.europa.eu/dataset/be02937c-5a08-4732-a24a-03e0a48bdcda) (detailed in E Silva et al. 2020) 


## Code organisation

Code is organized to reproduce per figure (3-6) in Lin et al. 2025
Fig 1 and 2 can be reproduced with the dataset deposited on Zenodo.

## References

References: 

De Ridder, K., Lauwaet, D., and Maiheu, B., (2015): UrbClim – A fast urban boundary layer climate model. *Urban Climate*, 12, 21–48. https://doi.org/10.1016/J.UCLIM.2015.01.001.

E Silva, B. et al. (2020). Uncovering temporal changes in Europe’s population density patterns using a data fusion approach. *Nature communications*, 11(1), 4631. https://doi.org/10.1038/s41467-020-18344-5

Hooyberghs, H., Berckmans, J., Lauwaet, D., Lefebre, F., and De Ridder, K., (2019): Climate variables for cities in Europe from 2008 to 2017. *Copernicus Climate Change Service (C3S) Climate Data Store (CDS)*. https://doi.org/10.24381/cds.c6459d3a.

Huang, W.T.K. et al. Economic valuation of temperature-related mortality attributed to urban heat islands in European cities. *Nature Communications* 14, 7438 (2023). https://doi.org/10.1038/s41467-023-43135-z

Masselot et al. (2023): Excess mortality attributed to heat and cold: a health impact assessment study in 854 cities in Europe, *The Lancet Planetary Health*, https://doi.org/10.1016/S2542-5196(23)00023-2. 
