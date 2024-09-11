# Our Foray into the Aircraft Business

Flatiron School Data Science: Phase 1 Project

    
* **Author:** Mohammad Abou-Ghazala <br/>
* **Instructor:** Mark Barbour <br/>
* **Pace:** Flex

![image](https://github.com/user-attachments/assets/269b37d4-5c37-4173-b4a8-1f0094ca8209)
Image source: [AirPartner](https://www.airpartner.com/en/aircraft-guide/)

## Overview
This project looks at data regarding reported aviation crashes since the 1940s, encompassing the details of the aircrafts, severity of the damage and injuries, weather during the incident, etc. <br/><br/>
_The original dataset can be found here:_ [Aviation Accident Database & Synopses](https://www.kaggle.com/datasets/khsamaha/aviation-accident-database-synopses?resource=download&select=AviationData.csv) <br/><br/>
Since my employers seek to invest in aircrafts, I distill this data into its most useful form, and provide a number of recommendations based on analysis of this distilled data, namely that I recommend: 
1) An aircraft with 2-4 engines.
2) An aircraft with the Turbo Fan type of engine.
3) The Cessna make of aircraft.

## Business Understanding
My company seeks to diversify its portfolio and expand into new industries. It wants to acquire and operate airplanes for commercial and private enterprise, though the company is not well-acquainted with the risks inherent in this endeavor.

My goal is to use the dataset provided to gain insight as to which airplanes the company's Head of Aviation Division should invest in.

## Data Understanding & Preparation
With over 88,000 entries and data encompassing more than 30 categories, the first move was to remove less-than-relevant data, such as "__purpose of flight__," "__location__," or "__airport name__." I also removed entries without entries for the critical categories, namely:
* Number of Engines
* Engine Type
* Injury Severity
* Aircraft Damage
* Total Injuries (Fatal, Serious, Minor) <br/>

Also, due to a change in flight standards and the like, we narrowed down the dataset to encompass __the years from 1982-2019__, and chose to exclude 2020 onwards due to a severe drop in air travel due to the global COVID pandemic. From there, I pulled from this dataset to create a few supplementary focused dataframes to more efficiently investigate the most frequently used aircraft makes and models, engine types, etc.

#### _Quantifying Damage Severity_
Under the category of "__Aircraft Damage__" were three main descriptors: Minor, Substantial, and Destroyed. To better get an understanding of the severity of damage to the aircrafts, I created a new column titled "__Damage Binary__" which rendered the result of "True" if the Aircraft Damage was Substantial or Destroyed, and False if the Aircraft Damage was Minor. From there, I assigned the number 1 to True results and 0 to False results, and used these numbers to extrapolate average aircraft damage severity in the data visualizations.

A more thorough accounting of the data cleaning and preparation process can be seen in the Jupyter Notebook [found here](https://github.com/momopajamas/Phase_1_Project/blob/main/Aircraft%20Damage.ipynb). 

#### _Confounding Factors_
As can be expected, there were a number of factors that were not accounted for in the original dataset that would reasonably assumed to have had an impact on the results and analysis, namely:
* Age of the aircraft
* Aircraft maintenance policies of the airlines
* Experience and talent of the pilot

## Data Modeling
Below, you will find data visualizations demonstrating the following: <br/>
1) Aircraft accidents that have the Turbo Fan engine type have much lower rates of serious and minor injuries, and higher rates of uninjured.
2) Aircrafts with 2-4 engines have lower rates of damage severity to the vehicles.
3) Upon considering the make of the aicraft in conjuunction with number of engines, Cessna aircrafts with 4 engines have the lowest rates of severe damage. <br/><br/>

![Dashboard 1](https://github.com/user-attachments/assets/b50eaf7a-50b3-49c5-9135-e007d5d726f3)


These visualizations can be accessed here: [Tableau Public Dashboard](https://public.tableau.com/app/profile/mohammad.abou.ghazala/viz/Phase1Project-TotalofInjuriesandUninjured/Dashboard1?publish=yes) 

## Conclusion & Recommendations

Upon investigating the cleaned data, a few clear connections can be seen, as demonstrated above.<br/>

According to these findings, I recommend the following guidance when considering new investments in airplanes: <br/>

1) Acquiring Cessna airplanes with 4 Turbofan engines is the safest option
2) Avoiding Reciprocating engine types
3) Acquiring an aircraft with at least 2 or more engines
