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
- There are clearly two classifications of votes. So the divide was Republican vs Democrat, or conservative vs. liberal, not subgroups within the parties or some other kind of grouping. However, some conservative Democrats were grouped with Republicans in the cluster model. This most likely reflects the characteristics of political parties during the particular time period of the dataset.
- The Random Forest model predicted who was a Republican and who was a Democrat equally well and did a good job.
- The greatest partisan divide even in 1984 was on health care policy. The budget resolution tends to be an expression of party priorities and was partisan enough that votes on it were a top predictor of who was a Republican or Democrat.


## Limitations

- There are 16 bills, a limited number. The selection process for the bills was important and was a major limitation. These were 16 key votes identified by the Congressional Quarterly Almanac.
- This is data for only one year
- The votes marked '?' fall into multiple categories
