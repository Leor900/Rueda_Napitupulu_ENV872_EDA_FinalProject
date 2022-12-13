# Rueda_Napitupulu_ENV872_EDA_FinalProject
Is air pollution correlated to interstate migration in the US? 
# Repository Title: Rueda_Napitupulu_ENV872_EDA_FinalProject

Title of the project: Is air pollution correlated to interstate migration in the US?

This project looks at the effects of air pollution on inter-state migration in the United States using the Air Quality Index datasets from EPA and the Population Migration data from the IRS for the period 2013-2020. Evidence from middle-income countries shows that air pollution has negative impacts on several health and economic outcomes, such as mortality rates, health expenditures, mental health, hours worked, labor productivity and income. 

Our hypothesis is that there is a positive relationship between high air pollution and migration outflows, that is, the highest the pollution registered by the Air Quality Index (AQI) in a state in a given year, the higher the number of people leaving that state the same year.


## Summary

This project analyzes the correlation between air quality and migration in the US in three categories. Air quality is measured as the Average by State of days classified as unhealthy, the average maximum AQI values reached by state, and the average days with PM2.5 registered in the air. The migration outflows are measured as the number of taxpayers whose domicile changes from one year to the other when submitting their tax returns. Based on the exploratory analysis and correlation above, there is a positive relationship between high air pollution and migration outflows. 

## Investigators

- Leonardo Rueda (jr466@duke.edu)
- Theo Napitupulu (yosia.napitupulu@duke.edu)
Sanford School of Public Policy, Duke University.

## Keywords

Air Pollution, Migration Outflows, Pearson's Correlation Test, Regression Analysis.

## Database Information

**1. Air Quality Datasets**

The Air Quality Index dataset provides annual information per county about the maximum values reached by the AQI, the number of days in which this index reached values considered unhealthy, and the number of days with PM2.5 particles recorded. The EPA's local air quality stations capture the information. Source: US Environmental Protection Agency. Air Quality System Data Mart [internet database] available at http://www.epa.gov/ttn/airs/aqsdatamart. Accessed December 01, 2022.

**2. Inter-state migration datasets**

The State-to-State outflow dataset provides annual information at the State level about the number of people whose reported home addresses changed in their individual income tax returns from one year to the other. Source: IRS. U.S. Population Migration Data. Available at: https://www.irs.gov/statistics/soi-tax-stats-migration-data. Accessed December 01, 2022.


## Folder structure, file formats, and naming conventions 

The repository contains three main folders: "Code", "Data", and "Output". 

Folder "Code" contains 4 files: 
- EDA_Final_Project.Rmd: This is the main file of the project and contains the codes to wrangle the datasets, make the tables, plots, and maps, and reproduce the final report. 
- EDA_Final_Project.log.
- EDA_Final_Project.pdf: This is the final knitted report, which contains the main findings of the project. 
- Project_Instructions.Rmd: contains the instructions provided by the professors. 

The folder "Data" contains the raw and processed datasets, as well as the dictionaries. It has three sub-folders: 

- "Dictionaries": contains the dictionary of the Migration Dataset. 
- "Processed": contains 3 datasets: 
    - "AQI_Mig.outflows_by.state_2013_2020.csv": The final dataset used in our analysis with the information aggregated by the state for the years 2013-2020. 
    - "Annual_AQI_by_state_2013_2020_Processed.csv": Dataset with the air quality information by county between 2012 and 2020. 
    - "Mig_outflows_by_state_2013_2020_Processed.csv": Dataset with the migration information by state between 2012 and 2020. 
- "Raw": contains 2 sub-sub-folders:
    - "Annual_aqi_by_county": contains 8 datasets in CSV format with annual information about air quality per county. 
    - "Outflows_by_state": contains 8 datasets in CSV format with annual information about migration outflows per state.
    ## Metadata

The variables in each of the files inside the folder "Data"/"Raw"/"Annual_aqi_by_county" are:

- file "annual_aqi_by_county_2013.csv": 
  - State: character variable that identifies the name of each state in the U.S.
  - County: character variable that identifies the name of each county in each state. 
  - Year: numeric variable that identifies the year.
  - Days with AQI: numeric variable that identifies the days in which the AQI was registered. 
  - Good Days: numeric variable that identifies the days in which the AQI was classified as "Good".
  - Moderate Days: numeric variable that identifies the days in which the AQI was classified as "moderate".
  - Unhealthy for Sensitive Groups Days: numeric variable that identifies the days in which the AQI was classified as "Unhealthy for Sensitive Groups".
  - Unhealthy Days: numeric variable that identifies the days in which the AQI was classified as "Unhealthy".
  - Very Unhealthy Days: numeric variable that identifies the days in which the AQI was classified as "very unhealthy".
  - Hazardous Days: numeric variable that identifies the days in which the AQI was classified as "Hazardous".
  - Max AQI: numeric variable that identifies the maximum AQI value reached.
  - 90th Percentile AQI: numeric variable that identifies the 90th percentile reached by the AQI.
  - Median AQI: numeric variable that identifies the median value reached by the AQI.
  - Days CO: Numeric variable that informs the number of days CO was detected in the air. 
  - Days NO2: Numeric variable that informs the number of days NO2 was detected in the air.
  - Days Ozone: Numeric variable that informs the number of days Ozone particles were detected in the air.
  - Days PM2.5: Numeric variable that informs the number of days PM2.5 was detected in the air.
  - Days PM10: Numeric variable that informs the number of days PM10 was detected in the air.

Note: The same variables are in the datasets for the years 2014-2020. 

The variables in each of the files inside the folder "Data"/"Raw"/"Outflows_by_state" are:

- file "stateoutflow1213.csv": 
  - y1_statefips: Numeric codes to identify each state.
  - y2_statefips: Numeric variable that informs the type of out-migration by state (total, same state, foreign, U.S.).
  - y2_state: character variable that identifies the abbreviated names of the states in the U.S.
  - y2_state_name: character variable that informs the type of out-migration by state (total, same state, foreign, U.S.).
  - n1: numeric variable that informs the number of tax returns submitted to the IRS.
  - n2: numeric variable that informs the number of individuals that submitted tax returns. 
  - AGI: numeric variable that informs the adjusted gross income of the individuals who submitted tax returns.
  - Year: numeric variable. 

Note: The same variables are in the datasets for the years 2014-2020. 

The variables contained in each of the files inside the folder "Data"/"Processed" are the following: 

- file "AQI_Mig.outflows_by.state_2013_2020.csv":
  - FIPS_Code: Numeric codes to identify each state. 
  - Year: numeric variable that identifies the year. 
  - State: character variable that identifies the name of each state in the U.S. 
  - Avg.Unhealthy.Days: Numeric variable that reflects the average per state and year of days with air quality considered as unhealthy.
  - Avg.Max.AQI: Numeric variable that calculates the average per state and year of the maximum values registered by the Air Quality Index (AQI). 
  - Avg.Days.PM2.5: Numeric variable that calculates the average per State and year of the number of days with PM2.5 detected in the air.
  - y2_state: character variable that identifies the abbreviated names of the U.S.
  - Migrants.outflows: numeric variable that identifies the number of migrants leaving each state per year. 
  
- file "Annual_AQI_by_state_2013_2020_Processed.csv":
  - State: character variable that identifies the name of each state in the U.S.
  - Year: numeric variable that identifies the year.
  - Avg.Unhealthy.Days: Numeric variable that reflects the average per state and year of days with air quality considered as unhealthy.
  - Avg.Max.AQI: Numeric variable that calculates the average per state and year of the maximum values registered by the Air Quality Index (AQI). 
  - Avg.Days.PM2.5: Numeric variable that calculates the average per State and year of the number of days with PM2.5 detected in the air.
  - FIPS_Code: Numeric codes to identify each state.
  
- file "Mig_outflows_by_state_2013_2020_Processed.csv":
  - FIPS_Code: Numeric codes to identify each state.
  - y2_statefips: numeric variable that informs the total out-migration by state.
  - y2_state: character variable that identifies the abbreviated names of the states in the U.S.
  - y2_state_name: character variable that classifies the type of migration per State. 
  - n1: numeric variable that informs the number of tax returns submitted to the IRS.
  - n2: numeric variable that informs the number of individuals that submitted tax returns. 
  - AGI: numeric variable that informs the adjusted gross income of the individuals who submitted tax returns.
  - Year: numeric variable. 

  
## Scripts and code

The folder "Code" contains the script of the project, called "EDA_Final_Project.Rmd". This script comprises the whole programming of the project. It includes data wrangling, data exploration, graphs, maps, correlation analysis, and regression analysis. 

