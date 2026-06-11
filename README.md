[![Run Notebook](https://github.com/eisenhauerIO/projects-businss-decisions/actions/workflows/run-notebook.yml/badge.svg)](https://github.com/eisenhauerIO/projects-businss-decisions/actions/workflows/run-notebook.yml)
[![Ruff](https://img.shields.io/endpoint?url=https://raw.githubusercontent.com/astral-sh/ruff/main/assets/badge/v2.json)](https://github.com/astral-sh/ruff)

# Uber Entry and Alcohol-Related Traffic Fatalities
## Overview 

This project replicates the main difference-in-differences analysis from Greenwood & Wattal (2017), which examines whether the introduction of Uber reduced alcohol-related traffic fatalities.

Using county-level data from California between 2010 and 2014, I estimate the effect of Uber's entry on alcohol-related traffic fatality rates. The analysis combines fatal crash data from the Fatality Analysis Reporting System (FARS), county population estimates from the U.S. Census Bureau, and Uber launch information across California counties.

The goal of this project is to determine whether increased access to ride-sharing services provided an alternative to drunk driving and ultimately improved traffic safety.

## Research Question

Does Uber's entry into a county reduce alcohol-related traffic fatalities?

## Data Sources

This project uses data from three primary sources:
* Fatality Analysis Reporting System (FARS)
* U.S. Census Bureau County Population Estimates
* Uber county entry and launch date information

The final dataset is organized at the county-year level and includes California counties from 2010 to 2014.

## Methodology

To estimate the impact of Uber's entry, I use a Difference-in-Differences (DiD) research design.
The analysis compares:
* Counties before and after Uber entered
* Relative to counties where Uber had not yet entered during the same period
The baseline model includes:
* County fixed effects
* Year fixed effects
* County-clustered standard errors

This approach helps isolate the relationship between Uber availability and alcohol-related fatality rates while controlling for county-specific characteristics and statewide trends.

## Tools Used

This analysis was completed in Python using:
* pandas
* numpy
* statsmodels
* matplotlib
* seaborn

## Results 

The baseline difference-in-differences model produced a negative coefficient on the Uber entry variable, suggesting that Uber's arrival may be associated with a decrease in alcohol-related traffic fatalities.

However, the effect was not statistically significant. While the results point in the direction of ride-sharing potentially reducing drunk driving, the evidence from this dataset is not strong enough to confidently conclude that Uber had a measurable impact on alcohol-related fatality rates in California during this time period.

To see whether the results were sensitive to different model specifications, I also conducted several robustness checks by:
* Restricting the sample to larger counties
* Using a log-transformed fatality rate

The results remained statistically insignificant across both alternative models, suggesting that the overall findings are consistent.

## Conclusion 
This project replicates the core empirical strategy from Greenwood & Wattal (2017) using county-level data from California. The results suggest that Uber entry is associated with a small reduction in alcohol-related traffic fatalities, but the estimated effects are not statistically significant.

Although the findings do not provide strong evidence that Uber reduced alcohol-related fatalities during this period, they are generally consistent with the idea that ride-sharing services could offer an alternative to driving after drinking.

Overall, this project demonstrates how difference-in-differences methods can be used to evaluate the real-world impact of new technologies and transportation services. Future research could expand the analysis to additional states, longer time periods, or explore whether the effects differ between urban and rural areas.

## References 
Greenwood, B. N., & Wattal, S. (2017). Show Me the Way to Go Home: An Empirical Investigation of Ride Sharing and Alcohol-Related Motor Vehicle Fatalities. MIS Quarterly, 41(1), 163–187.

Angrist, J. D., & Pischke, J.-S. (2009). Mostly Harmless Econometrics: An Empiricist's Companion. Princeton University Press.

Bertrand, M., Duflo, E., & Mullainathan, S. (2004). How Much Should We Trust Differences-in-Differences Estimates? Quarterly Journal of Economics, 119(1), 249–275.
