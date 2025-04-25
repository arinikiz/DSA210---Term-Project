# DSA210-Term-Project
Analysis of the relationship between political instability and terrorism as part of my Introduction to Data Science Course (DSA).


🟥**DISCLAMIER**:🟥    
**This study is conducted with an academic and analytical approach, aiming to understand the relationships between terrorism, governance, and political instability. The findings, interpretations, and conclusions presented are purely for research purposes and do not reflect any political stance or advocacy. This project unequivocally recognizes terrorism as a threat to stability and security, and any references to terrorist activities are solely for analytical purposes to contribute to a deeper understanding of their origins, aiding in the development of more effective prevention strategies.**  

🟢**LLM USAGE:** Large Language Models (LLMs) were utilized solely to assist with report writing. All data analysis, development of custom Python scripts, and hypothesis testing were conducted independently without any assistance from LLMs; every line of code was written by me🟢


## Overview

Terrorism remains one of the most pressing threats in the modern world, prompting extensive research over the years to uncover its underlying causes. Discovering these causes is imperative for developing proactive and preventative strategies rather than reactive, event-driven responses.  

In this regard throughout the course of a few months, using data visualization and statistical tools, I aim to examine"the extent to which political instability contributes to fueling terrorist activities worldwide. By the end of this project, I seek to answer a fundamental question: 
> Does political instability leads to increased terrorism ?

In order to reach an accurate conclusion, multiple datasets will be used from trusted, non-biased sources:

1. Uppsala Conflict Data Program (UCDP) by - by University of Uppsala (https://ucdp.uu.se/downloads/)
2. Control of Corruption (CC): Percentile Rank WGI - by World Bank Group (https://data.worldbank.org/indicator/CC.PER.RNK)
3. Rule of Law (RL): Percentile Rank WGI - by World Bank Group (https://data.worldbank.org/indicator/RL.PER.RNK)
4. Global Terrorism Database (GTD) - by University of Maryland (https://www.start.umd.edu/data-tools/GTD)


  
## Explanation of the Datasets

 **Uppsala Conflict Data Program (UCDP)**: The leading global source of data on organized violence and the longest-running civil war data collection initiative, spanning nearly 40 years.
 
 **Global Terrorism Database (GTD)**: An open-source database that documents over 200,000 terrorist incidents worldwide from 1970 to 2020, covering both domestic and transnational attacks. It provides detailed information on each event, including the date, location, weapons used, targets, casualties, and, when identifiable, the responsible group or individual.  
 
 **Control of Corruption (CC)**: Measures the extent to which public power is exercised for private gain, including both petty and grand forms of corruption, as well as "capture" of the state by elites and private interests. Countries are ranked from 0 to 100.  
 
 **Rule of Law (RL)**: Measures the extent to which agents have confidence in and abide by the rules of society, and in particular the quality of contract enforcement, property rights, the police, and the courts, as well as the likelihood of crime and violence. Countries are ranked from 0 to 100.  




~~## Initial Methodology (Not Definitive)~~

~~A multi-step approach will be followed to accurately answer the question posed in the overview section. Please note that this is a tentative methodology and is subject to change during the analysis of the data, depending on whether additional information is required.~~

~~### 1.Data Collection~~

~~From the above mentioned datasets, relevant data will be collected and filtered out accordingly using a custom script in Python.~~  

~~Filtering of the data is planned to be done in the following manner:~~
~~- Data from 2000 to the latest date that is available will be filtered out.~~
  ~~- CC: Percentile Rank and RL: Percentile Rank datasets provide data up until 2025.~~
  ~~- GTD provide data up until 2025~~
  ~~- UCDP provides data up until 2023.~~

~~- From UCDP:~~
  ~~- Not all conflicts provided in the data set will be used, rather the following conflicts will be filtered:~~
      ~~- Interstate Conflicts (between countries) (`type of conflict == 1`)~~
      ~~- Extra systemic conflicts (colonial wars or external invasions) (`type of conflict == 3`)~~
      ~~- One-sided violence (government attacking civilians) (`type of conflict == 5`)~~
  ~~- The official start date (`start_date`) and end date (`ep_end_date`), if any (`ep_end == 1`), of the conflicts will be extracted.~~
  ~~- Intensity levels of the conflicts will be extreacted:~~
      ~~- `intensity_level == 1` indicates minor armed conflict (25-999 battle-related deaths in a year).~~
      ~~-  `intensity_level == 2` indicates war (1,000+ battle-reated deaths in a year).~~
      ~~-  `cumulative_intensity` indicates the long-term intensity of the conflict (total battle deaths throughout the conflict).~~
  ~~- The names of the main actor initiating the conflict, the opponent in the conflict and the supporting parties will be extracted:~~
    ~~- `side_a` --> the main actor~~
    ~~- `side_a_2nd` --> second party supporting side A~~
    ~~- `side_b` --> the opponent~~
    ~~- `side_b_2nd` --> secondary party supporting the opponent~~  
    
- ~~From GTD:~~
    ~~- Year~~
    ~~- Month~~
    ~~- Involved country name~~
    ~~- Number of casualties~~  

~~- From CC and RL:~~
  ~~- Country name~~
  ~~- Percentile rank~~

~~### 2. Data Analysis~~

~~Using a custom Python script, the extracted data will be analyized to:~~  
~~1. Identify the terrorism hotspots via the extracted data from GTD.~~

~~2. Identify the political instability hotspots via the extracted data from CC, RL, and UCDP.~~


~~The classification of hotspots will be done in accordance with a classification method that will be developed by me. The classification method is as of right now undecided and will take its final form after the careful analysis of the extracted data. As an example:~~  

- ~~Terrorism hotspots can be classified using a straightforward threshold-based system. Countries exceeding a predefined number of X attacks per year and Y casualties due to terrorism can be categorized as hotspots.~~

- ~~Political instability hotspots can be classified using a point-based scoring system, where each predetermined criterion contributes a weighted score. Countries exceeding a certain threshold will be categorized as political instability hotspots.~~  

- ~~The findings from each dataset's exploratory data analysis (EDA), along with the metrics used to identify hotspots, will be documented in corresponding Markdown files.~~

~~### 3. Piecing Together the Findings~~

~~The findings from the analyzed data will be presented in a human-readable format using visual tools, and an accurate conclusion will be drawn.~~


## Updated Methodology

Prior to conducting exploratory data analysis (EDA), an initial tentative methodology was proposed to address the research question:
>  Does political instability leads to increased terrorism ?

Initially, this methodology described potential metrics and approaches for identifying Terrorism and Political Instability Hotspots to explore their causal relationship. However, following comprehensive exploratory analysis, significant revisions were made to refine and streamline this methodology into its final form.

The GTD, which contains detailed records of terrorist attacks from 1970 to 2020 (including ideological motivations, weapon types used, estimated property damage, etc.), was first explored. Relevant data was filtered to focus on each country's total number of attacks, the number of people wounded, and the number killed between the years 2000 and 2020.


The UCDP dataset provides information on both active and inactive conflicts involving states. Initially, it was considered to use this database to both measure political instability and support the identification of terrorism hotspots. However, the EDA revealed that integrating UCDP conflict data would introduce excessive complexity without proportionate benefit, making it more difficult to answer the research question effectively.

Therefore, the use of UCDP data was limited to analyzing intrastate conflicts (conflicts between a state and rebel groups) and internationalized intrastate conflicts (intrastate conflicts with foreign state involvement) occurring between 2000 and 2020. UCDP data offered valuable insights into conflict dynamics (such as start dates, durations, and annual intensity levels), even though it was ultimately not used to directly determine terrorism hotspots. These insights remain useful for deeper hypothesis testing later in the project.


In the course of the analysis, country-specific data for Türkiye was extracted. Türkiye was identified as a terrorism hotspot according to the evolving methodology. Further exploration of Türkiye's data provided an opportunity to deepen understanding of the datasets and to test the refined methodology.

**Note:** Findings and remarks for EDA analysis have been recorded in MarkDown files corresponding to each data set. (For instance, report on remarks and findings of the EDA analysis on GTD can be accessed from EDA_GTD >> GTD_findings.md)


To maintain analytical clarity and manageability without compromising accuracy, the revised methodology is outlined as follows:

1. **Identify Terrorism Hotspots**  
   From the GTD, select the **top 20 countries** based on the **frequency of terrorist attacks** between 2000 and 2020.  
   *Rationale:* Frequency of attacks provides a reliable, consistent metric for defining terrorism hotspots and supports longitudinal analysis.

2. **Select Sample Countries**  
   Randomly choose at least **five countries** from the identified terrorism hotspots for deeper analysis.

3. **For Each Selected Country:**
   - Extract additional information from the UCDP to be used as an aid, specifically:
     - Conflicts that **started**, **ended**, or were **ongoing** between 2000 and 2020.
     - **Annual conflict intensity** levels from 2000 to 2020.
     - **Rebel groups** involved during the period.
   - Extract **Rule of Law (RL)** and **Control of Corruption (CC)** indicators for the country from 2000 to 2020.

4. **Perform Hypothesis Testing**  
   Conduct hypothesis testing to assess the relationship between trends in terrorism and political instability for each country.

5. **Reach a Final Conclusion**  
   After analyzing at least five countries, synthesize findings and apply appropriate statistical analysis methods to answer the central research question.



## Next Steps

The analysis for Turkey has been completed. At least four additional countries will undergo the same rigorous analytical procedure. Final conclusions will integrate findings across multiple national contexts to robustly address the central research question.
  