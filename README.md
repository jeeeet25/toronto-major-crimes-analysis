# Toronot Major Crimes Analysis Project README

## Table of Contents
1. [Introduction](#10-introduction)
    1.1. [Data Source & Overview](#11-data-source--overview)
    1.2. [Business Problem Overview](#12-business-problem-overview)
    1.3. [Business Analytics Questions](#13-business-analytics-questions)
2. [Methodology - Approach & Reasoning](#20-methodology---approach--reasoning)
    2.1. [Data Cleaning and Transformation](#21-data-cleaning-and-transformation)
    2.2. [Data Visualization](#22-data-visualization)
    2.3. [Potential Solutions & Recommendations](#25-potential-solutions--recommendations)
    2.4. [Challenges](#26-challenges)
3. [Conclusion](#30-conclusion)

## 1.0. Introduction

The following report aims to provide an analysis of crime activity within the GTA (Greater Toronto Area) between the years 2017 and 2022. We have selected a data set from the official Toronto Police website. The data was cleaned and manipulated in order to create visualizations using Tableau. The goal is to provide the city of Toronto with clear visualizations of where and when most of the crime is taking place. This is done in order to implement appropriate actions to make Toronto a safer city.

### 1.1. Data Source & Overview

The dataset used in this analysis is obtained from the Toronto Police Department's official website [Toronto Police Department Data](https://data.torontopolice.on.ca/datasets/major-crime-indicators-open-data/explore?location=0.056066%2C159.045806%2C1.00&showTable=true). This dataset contains information about Major Crime Indicators (MCI) incidents and related offenses from 2014 to 2022. The included MCIs are Assault, Break and Enter, Auto Theft, Robbery, and Theft Over (excluding Sexual Violations). The data can be viewed at the offense or victim level, leading to multiple rows for one occurrence due to various MCIs. The data includes REPORT_DATE and OCC_DATE in the UTC time zone. Unfounded cases are excluded. The data aims to inform communities about public safety but is preliminary and might not be fully verified.

#### Dataset Fields/Columns:

- EVENT_UNIQUE_ID: A unique identifier for each individual event/incident in the dataset (Integer).
- REPORT_DATE: The date when the event was reported to the authorities (Date/Time).
- OCCURRENCE_DATE: The date when the actual occurrence of the event took place (Date/Time).
- OFFENSE: The specific criminal offense associated with the event (String).
- MCI_CATEGORY: The category of Major Crime Indicator (MCI) to which the event belongs, such as Assault, Break and Enter, Auto Theft, Robbery, or Theft Over (String).
- DIVISION: The division within the area covered by the Toronto Police Service where the event occurred (String).
- NEIGHBOURHOOD_158: The neighborhood (larger region) identified by a code or name where the event took place, using a 158-neighborhood classification (String).
- LONG_WGS84 and LAT_WGS84: The longitude and latitude coordinates in the WGS84 geographic coordinate system, respectively, indicating the approximate location of the event (Float).

### 1.2. Business Problem Overview

The Major Crime Indicators (MCI) dataset from 2014 to 2022 is now being used for public safety studies. Although this dataset has the potential to improve law enforcement tactics and neighborhood wellbeing, there isn't yet an optimized method for thorough examination. This has an impact on law enforcement organizations and the larger society that rely on successful crime prevention techniques. The allocation of resources, the detection of criminal trends, and community involvement are all impacted by the lack of insightful analysis.

In order to address this, we suggest creating a dynamic Tableau project that incorporates the MCI information and focuses on insights related to crime category, resource allocation, and crime trend analysis. This technology will enable law enforcement to make data-driven choices, allocate resources effectively, and develop strategies to address particular types of crime. In the end, this strategy will increase public safety, help law enforcement make more informed decisions, and promote a safer neighborhood.

### 1.3. Business Analytics Questions

The following analytical questions have been designed to facilitate the extraction of relevant insights from the data provided:

1) In what hours of the day does crime become more prominent?
2) Which neighborhoods have the highest crime rate?
3) Which crimes have been the most predominant between 2017 and 2022?
4) In what locations do the most predominant crimes take place?

## 2.0. Methodology - Approach & Reasoning

### 2.1. Data Cleaning and Transformation

We used Tableau Prep for cleaning and transformation. Following is the flow of data processing:

**Steps description:**
1. Import the CSV file and investigate its contents.
2. Transform date fields from string to date format.
3. Filter dates of offense (OCC_DATE) to the 5 last years and exclude null dates. This step eliminates rows with null values in other fields.
4. Remove unnecessary columns and rename some columns. For example, HOOD_140 and Neighborhood_140 are duplicated by HOOD_158 and Neighborhood_158 and represent an earlier version of Toronto Neighborhoods.
5. Make decisions on imputation. 1% of records have 0 latitude and corresponding NSA Neighborhood value. We decided to keep 0 values.
6. Inside Tableau, assign LAT and LONG geographic roles, Latitude and Longitude respectively, as there are no roles such as Longitude and Latitude in Tableau Prep.
7. Export into Tableau Data Extract.

### 2.2. Data Visualization

The following visualizations are directly linked to the analytical question regarding the most predominant crimes between the years 2017 and 2022:

[Insert relevant visualizations here with descriptions]

### 2.3. Potential Solutions & Recommendations

- Police training plan: If there are different training requirements for investigating and handling different crime categories, this visualization can enable the Toronto Police Department to optimize how many officers are trained to tackle the respective crime categories.
- Work Scheduling: Police officers with specific training for a crime category can be intelligently scheduled for periods characterized by larger volumes of crimes for the respective categories.
- Improved Policing & Crime Decline: A proper implementation of the above points combined can optimize and improve policing by placing the right officers at the right places and times. This can very easily translate to reduced crime rates.
- Improved surveillance: The City of Toronto could work with apartment residents and property management firms to implement improved security measures like CCTV cameras, access control systems, and well-lit common areas. The City could also adopt safety technologies like GPS trackers, immobilizers, and remote security systems to deter vehicle theft attempts.

### 2.4. Challenges

We encountered several challenges while analyzing this dataset due to its characteristics and considerations as follows:

1. Data Completeness and Accuracy: The dataset acknowledges that the data had not been entirely verified at the time of publication. This inaccuracy and incompleteness could lead to discrepancies and weaken the validity of the analysis.
2. Timezone Alignment: To preserve perfect anonymity, the REPORT_DATE, REPORT_HOUR, OCC_DATE, and OCC_HOUR were recorded in UTC time zone. The analysis, however, is concentrated on Toronto and the Eastern Time Zone.
3. Data Structure Complexity: Due to the offense and victim-level reporting, the dataset had many rows connected to a single occurrence number, which required advanced Tableau Prep techniques for cleaning.
4. Data Context and Verification: Drawing data-driven solutions and significant conclusions required extra caution because the data was preliminary and not fully confirmed.

## 3.0. Conclusion

Analyzing the major crime indicator's dataset can help law enforcement revise tactics and optimize resource allocation. The symbol map charts indicate that assault is most commonly occurring in specific locations in Wychwood. It may be influenced by a spatial correlation between crimes and areas of occurrence, but it doesn't describe the mechanism underlying the correlation. In order to further understand the root cause and assess alternative tactics, it is necessary to cross-relate them with other aspects of crime such as economic and demographic features, for example, employment levels and education levels. To improve the impact of law enforcer tactics and minimize the further increase of major crimes and keep Toronto a safe city.

