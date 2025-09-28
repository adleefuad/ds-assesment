
# Agent Persona Analysis
This project focuses on developing persona profiles for insurance agents through behaviour analysis. This assesment aim are to segment insurance agents into meaningful groups based on their characteristics, performance patterns, and working styles.


## Data Used
The data used as per given by AIA assesment.
Includes Agent Data, Historical Sold Policy, Main Need of each Policy

| File             | File                                                               |
| ----------------- | ----------------------------------------------------------------------- |
| Agent Data | ![AGENT.CSV](https://github.com/adleefuad/aia-assesment/blob/main/assessment_data/AGENT.csv) AGENT.CSV |
| Historical Sold Policy | ![MAIN.CSV](https://github.com/adleefuad/aia-assesment/blob/main/assessment_data/MAIN.csv) MAIN.CSV |
| Policy Main Group | ![B.CSV](https://github.com/adleefuad/aia-assesment/blob/main/assessment_data/B.csv) B.CSV, ![C.CSV](https://github.com/adleefuad/aia-assesment/blob/main/assessment_data/C.csv) C.CSV , ![D.CSV](https://github.com/adleefuad/aia-assesment/blob/main/assessment_data/D.csv) D.CSV, ![E.CSV](https://github.com/adleefuad/aia-assesment/blob/main/assessment_data/E.csv) E.CSV |


## Methodology
We use Clustering Method to segment the agents according to their behaviour

Possible Feature for agent persona (agent behaviour)
### Overall Policy Sold
1. Number of basic policies sold per agent
2. Median/Average number of riders per basic policy
### Portfolio Tendency
3. Ratio of LA
4. Ratio of LAT
5. Ratio of POLA
### MAIN_NEED Tendency
6. Ratio Medical
7. Ratio Life
8. Ratio Disability
9. Ratio Savers
10. Ratio Payor_Waiver
11. Ratio Critical_Illness
12. Ratio Accident
13. Ratio Income
14. Ratio Other_Medical
15. Ratio Endowment

### Time Sensitive Features
16. Median/Average number of policies sold per month 
17. Variance of number of policies sold per month
18. Duration of First Purchase to Last Purchase (Served Duration as Agent)


## Feature Correlations

![Feature Correlation](https://github.com/adleefuad/aia-assesment/blob/main/Model%20FineTuning%20And%20Evaluations.png)

## Model Evaluations
![FineTuning & Evaluations](https://github.com/adleefuad/aia-assesment/blob/main/Model%20FineTuning%20And%20Evaluations.png)