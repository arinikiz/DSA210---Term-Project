# DSA210-Term-Project
Analysis of the relationship between political instability and terrorism as part of my Introduction to Data Science Course (DSA).

🟥**DISCLAMIER**:🟥    
**This study is conducted with an academic and analytical approach, aiming to understand the relationships between terrorism, governance, and political instability. The findings, interpretations, and conclusions presented are purely for research purposes and do not reflect any political stance or advocacy. This project unequivocally recognizes terrorism as a threat to stability and security, and any references to terrorist activities are solely for analytical purposes to contribute to a deeper understanding of its origins to aid in more effective prevention strategies.**  


## Overview

Terrorism remains one of the most pressing threats in the modern world, prompting extensive research over the years to uncover its underlying causes. Discovering such causes are imperative in order to develop proactive and preventative strategies rather than reactive, event-driven responses.  

In this regard throughout the course of a few months, using data visualization and statistical tools, I aim to examine the extent to which political instability contributes to fueling terrorist activities worldwide. By the end of this project, I aim to answer a fundamental question: Does terrorism increase before instability rises, or does instability lead to more terrorism ?

In order to reach an accurate conclusion, multiple datasets will be used from trusted, non-biased sources:

1. Uppsala Conflict Data Program (UCDP) by - by University of Uppsala (https://ucdp.uu.se/downloads/)
2. Control of Corruption (CC): Percentile Rank WGI - by World Bank Group (https://data.worldbank.org/indicator/CC.PER.RNK)
3. Rule of Law (RL): Percentile Rank WGI - by World Bank Group (https://data.worldbank.org/indicator/RL.PER.RNK)
4. Global Terrorism Database (GTD) - by University of Maryland (https://www.start.umd.edu/data-tools/GTD)


  
## Explanation of the Datasets



## Initial Methodology (Not Definitive)

A multi-step approach will be followed to accuretly answer the question posed in the overview section. Please note that this is a tentative methodology and is subject to change during the analysis of the data, as more or less information may be needed. 

### 1.Data Collection

From the above mentioned datasets, relevant data will be collected and filtered out accordingly using a custom script in Python.  

Filtering of the data is planned to be done in the following manner:
- Data from 2000 to the latest date that is available will be filtered out.
  - CC: Percentile Rank and RL: Percentile Rank datasets provide data up until 2025.
  - GTD provide data up until 2025
  - UCDP provides data up until 2023.

- From UCDP:
  - Not all conflicts provided in the data set will be used, rather the following conflicts will be filtered:
      - Interstate Conflicts (between countries) (`type of conflict == 1`)
      - Extra systemic conflicts (colonial wars or external invasions) (`type of conflict == 3`)
      - One-sided violence (government attacking civillians) (`type of conflict == 5`)
  - The official start date (`start_date`) and end date (`ep_end_date`), if any (`ep_end == 1`), of the conflicts will be extracted.
  - Intensity levels of the conflicts will be extreacted:
      - `intensity_level == 1` indicates minor armed conflict (25-999 battle-related deaths in a year).
      -  `intensity_levle == 2` indicates war (1,000+ battle-reated deaths in a year).
      -  `cumulative_intensity` indicates the long-temr intensity of the conflict (total battle deaths throughout the conflict).
  - The names of the main actor initiating the conflict, the opponent in the conflict and the supporting parties will be extracted:
    - `side_a` --> the main actor
    - `side_a_2nd` --> second party supporting side A
    - `side_b` --> the opponent
    - `side_b_2nd` --> secondary party supporting the opponent  
    
- From GTD:
    - Year
    - Month
    - Involved country name
    - Number of causilties  

- From CC and RL:
  - Country name
  - Percentile rank

### 2. Data Analysis

Using a custom Python script, the extracted data will be analyized to:  
1. Identify the terrorism hotspots

2. Identify the political terrorism hotspots  


The classification of hotspots will be done in accordance with a classification method that will be developed by me. The classification method is as of right now undecided and will take its final form after the careful analysis of the extracted data. As an example:  

The terrorism hotspots may be classified based upon a simple comparision system .........  

The political instability hotspots will be classified based upon a pooint based system where .......

### 3. Piecing Together the Findings
