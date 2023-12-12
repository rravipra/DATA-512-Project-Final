# DATA-512-Project Final

# Goal:

The goal of this project is to answer a few research questions based on the wildfire smoke impacts in Helena, Montana.

The primary goals of this project are informed by extensive research in the field of wildfire analysis and its impacts on urban areas and public health. The study leverages historical data and prior research to delve deeper into the changing dynamics of wildfire behavior and its implications. It aims to extend the existing knowledge base by addressing specific research questions that focus on long-term impacts of wildfires on communities, ecosystem health, and public safety in Helena, Montana. The specific goals aligned with our research questions are as follows:

First, the goal is to create an annual estimate of wildfire smoke in Helena, Monatana. This estimate is just a number that you can eventually use to build a predictive model. Technically, smoke impact should probably be considered the health, tourism, economic or other social problems that result from the smoke. For this we'll generically call your estimate the wildfire smoke impact. We need some kind of number to represent an estimate of the smoke your city saw during each annual fire season.

Further, another thing is trying to understand how good or bad your smoke estimate might be. Once you have developed your smoke estimate, you should compare your estimate to available AQI (Air Quality Index) data from the US EPA. The US EPA was only created in 1973, and did not really begin installing air quality monitoring stations until the early 1980s. Further, of 3000+ counties in the US, the EPA has vetted monitoring stations in only 2000 of them which is why we can't just use the AQI as an estimate for smoke impact. This means that US EPA AQI measures for any one city will need to be some kind of estimate based on monitoring stations that are nearby.

The smoke estimate adheres to the following conditions:
1. The estimate only considers the last 60 years of wildland fires (1963-2023).
2. The estimate only considers fires that are within 1250 miles of your assigned city.
3. An annual fire season will run from May 1st through October 31st.

Below are the research questions that I am trying to answer in this project:

1. **Estimate Smoke Impacts Over 60 Years**:
   - **Objective**: To quantify the historical impact of wildfire smoke on Helena, Montana, over the last 60 years, providing insights into trends and changes during this period.
   - **Significance**: This analysis will enhance understanding of how wildfire smoke has affected Helena, aiding in the development of more effective mitigation and adaptation strategies.

2. **Predict Child Mortality Rates for the Next 25 Years**:
   - **Objective**: To forecast the impact of wildfire smoke on child mortality rates in Helena for the next 25 years.
   - **Significance**: This prediction is crucial for public health planning, focusing on protecting the most vulnerable populations from the adverse effects of wildfire smoke.

3. **Assess Changes in Health and Healthcare Demand**:
   - **Objective**: To examine how the number of people with poor health and the number of patients seen by primary care physicians have changed over recent years in Helena.
   - **Significance**: This analysis will provide insights into the broader health impacts of wildfires, exploring the correlation between fire events and the health status of the local population.

4. **Estimate Future Healthcare Needs**:
   - **Objective**: Based on estimates of child mortality rates due to smoke exposure and general health trends, to predict the number of patients to be seen and the number of doctors/health care providers required in the future in Helena.
   - **Significance**: This goal aims to translate health impact estimates into actionable insights for healthcare planning, ensuring the community is well-equipped to handle future challenges posed by wildfires.

These goals are critical for understanding the long-term effects of wildfires on urban centers like Helena, Montana. They aim to bridge the gap between historical data and future planning, offering a comprehensive view of the challenges and necessary responses to mitigate the impact of wildfires on public health and safety.

Here is a link to the repository of the part 1 of this analysis project: [link](https://github.com/rravipra/DATA-512-Project/tree/main)

# Data:

Wildfire dataset: https://www.sciencebase.gov/catalog/item/61aa537dd34eb622f699df81 from here download the GeoJSON Files.zip and use the USGS_Wildland_Fire_Combined_Dataset.json data.

Example notebooks epa_air_quality_history_example.ipynb and wildfire_geo_proximity_example.ipynblicensed by: [Creative Commons](https://creativecommons.org) [CC-BY license](https://creativecommons.org/licenses/by/4.0/)

Air Quality System (AQS) API: [Documentation](https://aqs.epa.gov/aqsweb/documents/data_api.html)

Additional information on AQS: [here](https://www.epa.gov/outdoor-air-quality-data/frequent-questions-about-airdata)

I have downloaded all the three dataset from here for the extension plan: https://datausa.io/profile/geo/lewis-and-clark-county-mt
The datasets can be found in Data_files in the repository and are Clinical Care.csv, Health Outcomes_child_mortality.csv, Health Outcomes_poor_fair_health.csv

Licensing for the datasets for the datasets extension plan: https://www.countyhealthrankings.org/terms-use

# Code files:

The notebooks file in this repository are:

- Calculate_smoke_impact.ipynb
- Calculate_AQI_estimate.ipynb
- Extension_plan.ipynb

(These below two code example was developed by Dr. David W. McDonald for use in DATA 512, a course in the UW MS Data Science degree program. This code is provided under the [Creative Commons](https://creativecommons.org) [CC-BY license](https://creativecommons.org/licenses/by/4.0/). Revision 1.0 - August 13, 2023
- epa_air_quality_history_example.ipynb
- wildfire_geo_proximity_example.ipynb
- wildfire.zip

# Data Files created from the code:

1) acres_burned_annual.json
2) annual_smoke_impact_final.json
3) fire_counts_final.json

The acres_burned_annual.json is the file that is used to create the graph of the total area of the fires for a given year and the fire_counts_final.json consists of the total number of fires of a given year over the years 1963-2023 within 1250 miles of Helena, Montana.

The annual_smoke_impact_final.json consists of the smoke estimates that is calculated for each year from 1963-2023 for Helena, Monatana.

**Structure of the JSON files:**

For the smoke impact estimation

**Key**: Years

**Value**: A list of estimate values.

For the acres_burned_annual.json and 

**Key**: Years

**Value**: acres burened

For the fire_counts_final.json

**Key**: Years

**Value**: counts of the number of fires.

# Images of graphs acquired from the code outputs:

The code also outputs many graphs which is present and is mentioned in detail in the Final_report pdf in this repository. (Note: every image/visualization in the final report pdf is acquired from the code outputs)

Time series prediction for the next 25 years based on the smoke impact estimate: You can find the code in Calculate_AQI_estimate.ipynb:

![image](https://github.com/rravipra/DATA-512-Project/assets/46725716/c716b018-4777-48c4-b148-1014559d7089)

The prediction of the child mortality rates for the next 25 years based on the smoke impact estimates.

![512_2](https://github.com/rravipra/DATA-512-Project-Final/assets/46725716/a2b8bfd3-0c89-48bc-8b3c-0ccce56d2119)

# Considerations with the Data:

- It is important to note that the when it comes to calculating the smoke impact estimates for each of the years, in my case I did not have the data for the years 2021, 2022, and 2023 so my estiamtes was only from 1963-2020.
- Even in the data to get the AQI scores while getting the Gaseous AQI pollutants and the Particulate AQI pollutants it is not necessary that the data for both are present for all the years. I only found data for both from 1986-2023 which I have used.
- It is also important to notice that you will not get the AQI scores for a given year from each and every station nearby so you will have to improvise on that based on what would work best for you.
- It is also important to consider the fact that the data files that I have used for my extension plan are all at a county level which is for Lewis and Clark county where Helena, Montana is located, if you are able to find the data at a city level that would be great as well and might be better for the analysis.


