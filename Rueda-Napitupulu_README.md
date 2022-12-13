# Rueda_Napitupulu_Project
Is air pollution correlated to interstate migration in the US?

This project looks at the effects of air pollution on inter-state migration in the United States using the Air Quality Index datasets from EPA and the Population Migration data from the IRS for the period 2013-2020. Evidence from middle-income countries shows that air pollution has negative impacts on several health and economic outcomes, such as mortality rates, health expenditures, mental health, hours worked, labor productivity and income. 

According to OECD, Fine particulate matter (PM2.5) is a serious pollutant globally that the chronic exposure even to moderate levels of PM2.5 substantially will increase the risk of heart disease and stroke, the leading causes of death in OECD countries. It also increases the risk of respiratory diseases, including lung cancer, chronic obstructive pulmonary disease and respiratory infections. Black carbon, a major component of PM2.5, accelerates global warming and fosters melting snow. Emissions from transport, industry, electricity generation, agriculture and domestic (household) sources are the main contributors to outdoor air pollution (see OECD (2022), "Air quality", in Environment at a Glance Indicators, OECD Publishing, Paris, https://doi.org/10.1787/80661e2d-en (accessed on 12 December 2022)).

Additionally, other studies have shown how migration decisions are affected by air pollution. For instance, Chen, S., Oliva, P., & Zhang, P. (2022) found that a 10 percent increase in air pollution, holding everything else constant, reduces population through net outmigration by about 2.8 percent in a given county in China (see Chen, S., Oliva, P., & Zhang, P. (2022). The effect of air pollution on migration: Evidence from China. Journal of Development Economics, 156, 102833. https://doi.org/10.1016/j.jdeveco.2022.102833).

Our hypothesis is that there is a positive relationship between high air pollution and migration outflows, that is, the highest the pollution registered by the Air Quality Index (AQI) in a state in a given year, the higher the number of people leaving that state the same year.


## Summary

<describe the purpose of this repository, the information it contains, and any relevant analysis goals. What, why, where, when, how?>
The main purpose of this project is to see whether any correlation between air quality and the migration in the US over the year of 2013 and 2020. It could be used as an alternative consideration for policymakes and other stakeholders to conduct relevant actions such as regulations, cost on public health, business decisions and other actions.
Additionally, The most recent Global Burden of Disease (GBD) study estimates that air pollution – indoor and outdoor combined – was the cause of 5.5 million premature deaths globally in 2013. Air pollution also has further consequences on human health, leading in particular to an increasing number of respiratory and cardiovascular diseases. Moreover, it affects crop yields and the environment, with impacts on biodiversity and ecosystems, amongst others. These impacts have significant economic consequences, which will affect economic growth as well as welfare (Source: OECD (2016), The Economic Consequences of Outdoor Air Pollution, OECD Publishing, Paris, https://doi.org/10.1787/9789264257474-en.).
This project analyzes the correlation between air quality and the migration in the US in three categories (Avg. unhealthy days, Avg. maximum AQI, Avg. days PM2.5). Based on the exploratory analysis and correlation above, there is a positive relationship between high air pollution and migration outflows. The pollution registered by the Avg. unhealthy days and Avg. maximum AQI in a state in a given year shows a positive correlation to the migrant outflows with respectively a small p-value 2.609e-09 and 1.558e-07. Meanwhile, despite according to the plot it seems slightly decreasing through the years, the Avg. days PM2.5 has a negative correlation to the migrants outflows. Therefore, these findings can become material for discussion for further research and see whether the increase in PM 2.5 contributes positively to outflow migration in the US.

## Investigators

- Leonardo Rueda (r466@duke.edu)
- Theo Napitupulu (yosia.napitupulu@duke.edu)
Sanford School of Public Policy, Duke University.

## Keywords

Air Pollution, Migration, healthy air, PM2.5 emission levels and intensities, Air Quality Index (AQI).

## Database Information

**1. Air Quality Datasets**

The Air Quality Index dataset provides annual information per county about the maximum values reached by the AQI, the number of days in which this index reached values considered unhealthy, and the number of days with PM2.5 particles recorded. The information is capture by the EPA local air quality stations. 
(Source: US Environmental Protection Agency. Air Quality System Data Mart [internet database] available at http://www.epa.gov/ttn/airs/aqsdatamart. Accessed December 01, 2022).

**2. Inter-state migration datasets**

The State-to-State outflows dataset provides annual information at the State level about the number of people whose reported home address changed in their individual income tax returns from one year to the other. The migration patterns for inflows is the number of new residents who moved to a State or county and where they migrated from, and the outflows is the number of residents leaving a State or county and where they went. (These datasets are available at https://www.irs.gov/statistics/soi-tax-stats-migration-data. Accessed December 01, 2022).


## Folder structure, file formats, and naming conventions 

Folder Code contains the rmd files of instructions and project worksheet including the knitted pdf file generated from the worksheet.
Folder Data has various raw datasets, dictionaries and processed data which is downloaded from multiple sources throughout websites in csv formats. The explanation fo file Air Quality datasets in csv format can be found at https://aqs.epa.gov/aqsweb/airdata/FileFormats.html).

## Metadata
The Air Quality Index dataset provides annual information per county about the maximum values reached by the AQI, the number of days in which this index reached values considered unhealthy, and the number of days with PM2.5 particles recorded. These datasets are available at https://aqs.epa.gov/aqsweb/airdata/download_files.html. 

The migration patterns for inflows is the number of new residents who moved to a State or county and where they migrated from, and the outflows is the number of residents leaving a State or county and where they went, includes: Number of returns filed, which approximates the number of households that migrated; Number of personal exemptions claimed, which approximates the number of individuals; Total adjusted gross income, starting with Filing Year 1995; Aggregate migration flows at the State level, by the size of adjusted gross income (AGI) and age of the primary taxpayer, starting with Filing Year 2011.

## Scripts and code

library('dplyr')
library('plyr')
library('ggplot2')
library('tidyverse')
library('rvest')
install.packages('usmap')
library('usmap')
library('viridis')
library('scales')
library('cowplot')

## Quality assurance/quality control

<describe any relevant QA/QC procedures taken with your data. Some ideas can be found here:>