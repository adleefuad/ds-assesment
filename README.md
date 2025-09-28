
# Agent Persona Analysis
This project focuses on developing persona profiles for insurance agents through behaviour analysis. This assesment aim are to segment insurance agents into meaningful groups based on their characteristics, performance patterns, and working styles.


## Data Used
The data used as per given by AIA assesment.
Includes Agent Data, Historical Sold Policy, Main Need of each Policy

| File             | File                                                               |
| ----------------- | ----------------------------------------------------------------------- |
| Agent Data | ![AGENT.CSV](https://github.com/adleefuad/aia-assesment/blob/main/assessment_data/AGENT.csv)|
| Historical Sold Policy | ![MAIN.CSV](https://github.com/adleefuad/aia-assesment/blob/main/assessment_data/MAIN.csv)  |
| Policy Main Group | ![B.CSV](https://github.com/adleefuad/aia-assesment/blob/main/assessment_data/B.csv) , ![C.CSV](https://github.com/adleefuad/aia-assesment/blob/main/assessment_data/C.csv) , ![D.CSV](https://github.com/adleefuad/aia-assesment/blob/main/assessment_data/D.csv), ![E.CSV](https://github.com/adleefuad/aia-assesment/blob/main/assessment_data/E.csv)|


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
16. Median and Standard Deviation number of policies sold per month 
17. Variance of number of policies sold per month
18. Duration of First Purchase to Last Purchase (Served Duration as Agent)


## Feature Correlations

![Feature Correlation](https://github.com/adleefuad/aia-assesment/blob/main/reference/image/Model%20FineTuning%20And%20Evaluations.png)

## Model Evaluations
![FineTuning & Evaluations](https://github.com/adleefuad/aia-assesment/blob/main/reference/image/Model%20FineTuning%20And%20Evaluations.png)

## Jupyter File Run Manual

1. create python virtual environment using python=3.11
```bash
  conda create -n aia-assesment python=3.11 -y
```
2. install the library
```bash
  pip install -r requirements.txt
```
3. Select Kernel to use the created virtual environment
4. To test with another dataset, Input your file here
![Jupyter Line read csv file](https://github.com/adleefuad/aia-assesment/blob/main/reference/image/file_loading.png)

5. Run the whole Data Preparation Section
6. Run the whole Feature Engineering Section 
7. Run the Clustering Section to get the predictions output

## Agent Persona Class
Since I am insufficient of time, I will use the description of the data for each Cluster. I should do more detailed analysis and graph to justify my reasoning and for more presentable to non technical stake holder.

After Doing the analysis with the clustering output here are the interpretations for each clustering:

1. (Takaful Player) - Where Agent Focus in LA Takaful Portfolio , Majorly policies involved Disability , Life and Medical
2. (Accident Insurer) - Agent Who Main Focus is using POLA Portfolio , Majorly involved Accident Policy
3. (Experienced Life Player) - Agent Who Main Focus is LA Portfolio, and the Policy is well distributed across all needs following the overall MAIN_NEED distributions, these agents are more than 1 year served as agent.
4. (New Agents) - Early Agents who mainly focus on Client who seek Medical Insurance

## Agent Categorical Scoring
Since I dont have sufficient time to do this use case, I will explain my approach here. In my mind there are two ways I want to approach

1. Is using simple statistical distribution of PROD_CAT for each agent and then the score is the ranking of the distribution of it. If the agents has insufficient data as in very less policy sold. We could use the general of all agents PROD_CAT distributions.
2. Use Classification Model (Linear Regression /  LigthGBM) using the same feature as my clustering and use the target column is the PROD_CAT. The output for each agent is that it will show the probability of each category. Then we use the output as scoring.

I think for this current use case , I think No.1 approach is more logical since to train ML model for 3000+ rows may not sufficient.

## Improvement Planning
1. I dont include the Vitality product in the clustering model. Need to study more on that
2. I need to understand ANP logic more to implement to the model

## Acknowledgement
All of the source code is written by me with the help of ChatGPT (especially in the plotting parts).
You can read my thought process and my process to reach to my conclusions in here: ![Jupyter File](https://github.com/adleefuad/aia-assesment/blob/main/analysis.ipynb)