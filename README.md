# Summary

This is a project that analyzed the data available at https://archive-beta.ics.uci.edu/ml/datasets/105 

I did extensive EDA, created a classification model, and evaluated the potential of clustering

# Navigating the notebooks

1. Run Import-EDA.ipynb
2. Run any of the other notebooks
    - other-EDA-visualizations.ipynb has prettier and more complex visualizations
    - classification-models.ipynb runs through a full process of classification modeling, including describing variables of interest, looking for outliers, setting up a dataframe for modeling, fitting and scoring models, making inferences
    - cluster-models.ipynb is where I evaluate the potential of cluster models
    
# Data folder

- house-votes-84.data has the raw data for the project
- house-votes-84.names has information about the dataset

# Executive Summary of Project

## Goal

The goal for the project was to predict whether a member of congress was a democrat or republican based on their voting record. It was also to find any other interesting patterns in this voting data, including the possible existence of more than two voting blocs. The data was from the 1984 House voting records. It had yes, know, and unknown/neutral votes from 16 key votes identified by the Congressional Quarterly Almanac.

There were two models:

1. For the classification model, the goal was to predict whether a member of congress was a Republican or Democrat based on their voting record. 

2. For the cluster models, the goal was to see if there were just 2 clusters of congressmembers, or if there was evidence of more clusters.



## Metrics

1. For the classification models, my main metric was an F1 score for the classification models that I tested. I used this because it seems to be the most common evaluation metric for classification models. It takes both the false negatives and false positives into account when evaluating how well the model predicts the positive class. However, choosing a positive and negative class was somewhat arbitrary. I also needed to evaluate the model in terms of accuracy for predicting who is a Republican and accuracy for predicting who is a Democrat, which meant comparing recall and specificity. I looked at overall accuracy and precision as well.


2. For the cluster modeling, I used two metrics. First, I made an elbow plot using the inertia score metric over a range of cluster numbers. The inflection point, or 'elbow', of the plot is the best cluster number. Second, I examined silhouette scores over a range of cluster numbers. The highest silhouette score is best.


## Findings

- Votes that unified Republicans: yes vote on the crime bill - bill passed, yes vote on physician fee freeze bill - bill didn't pass
- Democrats generally had more mixed votes
- The El Salvador aid bill, physician fee freeze bill, education spending, adoption of the budget resolution stand out as partisan in EDA
- There are clearly two classifications of votes. So the divide was Republican vs Democrat, not subgroups within the parties or some other grouping. More specifically, the divide was conservative vs. liberal, as a relatively small but significant number of conservative Democrats clustered with Republicans, which says more about political parties in 1984 than anything else.
- The Random Forest model predicted who was a Republican and who was a Democrat equally well and did a good job.
- The greatest partisan divide even in 1984 was on health care policy. The budget resolution tends to be an expression of party priorities and was partisan enough that votes on it were a top predictor of who was a Republican or Democrat.


## Limitations

- There are 16 bills, a limited number. The selection process for the bills was important and was a major limitation. These were 16 key votes identified by the Congressional Quarterly Almanac.
- This is data for only one year
- The votes marked '?' fall into multiple categories
    - Voted present because of conflict of interest or other reason
    - “Did not vote or otherwise make a position known”


# Data Dictionary

|Feature|Type|Description|
|---|---|---|
|party|object|Target, democrat or republican|
|handicapped-infants|object|congressmember vote on key bill "handicapped infants"|
|water-project-cost-sharing|object|congressmember vote on key bill "water project cost sharing"|
|adoption-of-the-budget-resolution|object|congressmember vote on the budget resolution|
|physician-fee-freeze|object|congressmember vote on key bill "physician fee freeze"|
|el-salvador-aid|object|congressmember vote on key bill "El Salvador aid"|
|religious-groups-in-schools|object|congressmember vote on key bill "religious groups in schools"|
|anti-satellite-test-ban|object|congressmember vote on key bill "anti satellite test ban"|
|aid-to-nicaraguan-contras|object|congressmember vote on key bill "aid to nicaraguan contras"|
|mx-missile|object|congressmember vote on key bill "mx missile"|
|immigration|object|congressmember vote on key bill "immigration"|
|synfuels-corporation-cutback|object|congressmember vote on key bill "synfeuls corporation cutback"|
|education-spending|object|congressmember vote on key bill "education spending"|
|superfund-right-to-sue|object|congressmember vote on key bill "superfund right to sue"|
|crime|object|congressmember vote on crime bill|
|duty-free-exports|object|congressmember vote on key bill "duty free exports"|
|export-administration-act-south-africa|object|congressmember vote on key bill "export administration act South Africa"|