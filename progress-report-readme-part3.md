# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Part 3: EDA + Preliminary Analysis

## Progress Report

This is an straightforward dataset to work with, on votes on bills for members of congress. There are 16 columns plus a target column. All of the columns are binary. The 16 columns are yes or no votes on bills, or a question mark. 

A main challenge/limitation is figuring out what to do with the cells with a question mark. These are not null data. Instead they are where a congress member voted present, voted present to avoid conflict of interest, and did not vote or otherwise make a position known. For some of the descriptive work and EDA, I made a yes vote 1 and a no vote or question mark zero. I think I will mostly be modeling with data where I have gotten dummies from the yes, no, and question marks so that I leave all of the data in instead of removing the question mark data.

To find outliers, I looked for highly unusual Democrats and Republicans. I split the data into Republican and Remocratic members. I binarized the feature data so that yes votes were 1 and other votes were 0. I then got the sums for each of the congressmembers. I didn't find outliers that I needed to worry about with this approach.

I mainly analyzed the distributions of votes for each bill, and did find one outlier in this analysis, 'export-administration-act-south-africa'. There are relatively few '?' votes and no votes compared to yes votes. No other column has a distribution that has this level of imbalance. I may want to drop this column.

I analyzed the distributions of votes for each bill for the whole dataset, just for Democrats, and just for Republicans. I found a couple of patterns in the distributions of votes for the whole dataset, however, the findings for Democrats and for Republicans are particularly helpful for modeling. First, most of the votes had a partisan split but some did not and some had a partisan split that was not overwhelming. However, most of the Republicans voted yes on the crime bill, the El Salvador aid bill, and the physician fee freeze bill. When I looked at the data for Democrats and compared it to the data for Republicans, the El Salvador aid bill, the physician fee freeze bill, education spending, and adoption of the budget resolution seemed to distinguish the two classes for my target variable.


## Next Steps

The EDA suggests that feature selection will be important. There are patterns in the votes that I can see from looking at overall distributions of yes, no and unknown votes for each bill. It also seems like a handful of bills were more partisan than the others, with very different votes from Republicans and Democrats. It could be interesting to do PCA. 

Three concrete actions:

1. Create dummies on the whole dataframe so that I can model with it
2. Test a range of classification models, looking at the predictive value of the model and classification metrics
3. Test the best classification models on different collections of features



## Overview

Begin quantitatively describing and visualizing your data. With rich datasets, EDA can go down an endless number of roads. Maintain perspective on your goals and scope your EDA accordingly. 

Managing your own time is a critical skill in analysis projects. Keep notes on your approach, results, setbacks, and findings! These will form the basis of your "progress report" to us for Part 3, as you meet with your instructors to discuss how things are going and what to do next.

**Goal**: A brief report that describes your EDA and analysis so far, as well as your concrete next steps.

---

## Requirements

1. Create a "progress report" that documents:
   - Your approach to exploratory data analysis
   - Your initial results
   - Any roadblocks, setbacks, or surprises
   
2. Perform initial descriptive and visual analysis of your data.
   - Identify outliers
   - Summarize risks and limitations 

3. Discuss your proposed next steps
   - Describe how your EDA will inform your modeling decisions
   - What are three concrete actions you need to take next?



## Project Feedback + Evaluation

[Attached here is a complete rubric for this project.](./capstone-part-03-rubric.md)

Your instructors will score each of your technical requirements using the scale below:

Score  | Expectations
--- | ---
**0** | _Incomplete._
**1** | _Does not meet expectations._
**2** | _Meets expectations, good job!_

## PROGRESS REPORT
**Student Check-in:**

|WHAT’S GOING WELL/STRUGGLES|DEVELOPMENT PLAN|INSTRUCTOR FEEDBACK|
|---------------------------|----------------|-------------------|
|                           |                |                   |
