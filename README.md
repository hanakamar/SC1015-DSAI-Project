# SC1015 Mini Project: Social Media & Fashion
----
School of Computer Science and Engineering  
Nanyang Technological University  
Group: 4
## Members:
> 1. Balasubramanian Roopashanthoshini (U2323844J)
> 2. Dhanapalan Swaminathan Sudhsishna Janavi (U2320155K)
> 3. Kamarudeen Hana Fathima (U2323533G)
## Table of Contents
> 1. Data Preparation and Cleaning
> 2. Exploratory Data Analysis
> 3. Anomaly detection
> 4. Insights from relationships in raw dataset
> 5. Clustering
## Problem Definition
Our aim is to use data collated from instagram posts from fashion influencers characterized by their features, such as user details, image features and features of the fashion item to accurately determine what metrics can effectively predict post popularity and subsequently, what metrics are most valuable to fashion brands looking to advertise on Social Media and leverage influencer marketing.
## Dataset
> Ha, Yu-i; Kwon, Sejeong; Cha, Meeyoung; Joo, Jungseock, 2017, "Fashion conversation data on Instagram", https://doi.org/10.7910/DVN/K7AW6F, Harvard Dataverse, V1, UNF:6:a/JWNHEGsJreZVqhBkLhgg== [fileUNF]
---
## 1. Data Preparation and Cleaning
In this file, we prepped and cleaned our dataset to work with it in the subsequent files. This involved:
> - Sanity checks for duplicate and missing values
> - Isolating numeric variables which we needed to work with in our dataset
> - Segregating the entire dataset into 4 sections; each uniqe brand category for deeper, specific exploration into each
> - Removing outliers by using a personalized function
> - Conversion of each dataframe to separate CSV files
## 2. Exploratory Data Analysis
In this file, we conducted a prelimiary exploration into our dataset to further determine which direction to take, which variables have correlations worth exploring & visualizing our conclusions. We accomplished this by:
> - Univariate exploration of our response variable - 'Likes' (Number of likes on a post)
> - Correlation charts with values on what variables had strongest correlations with Likes for our original and cleaned datasets
> - Visualizing top variables with correlations for each brand category

We concluded that Likes was an extremely narrow variable ranging from 10-50 but with lots of outliers that may skew the dataset. Hence when we visualized the correlations for both original and cleaned dataset - we found that correlations were much stronger, and distinct for our original dataset compared to that of the cleaned, which led us to discard the cleaned dataset and focus on the original one. We further visualized top variables that correlated well with Likes - Followers & Comments - and we found they too were narrow variables accorss the board for each brand category.
## 3. Anomaly Detection
In this file, we try outlier removal by anomaly detection using the isolating forests method as a fail-safe to ensure using the original dataset is more optimal than the cleaned dataset. This was executed by:
> - Creating a cleaned dataset by the isolating forests technique
> - Identifying outliers produced by this method
> - Computing correlations to likes in each brand category with this new cleaned dataset
> - Identifying top 4 variables with strongest correlations

By producing a cleaned dataset and computing correlations, we've compiled 3 datasets - the raw one and two cleaned (using IQR and isolated forests technique) and we've found correlations varied significantly across the three and that the removal of outliers may have been responsible for the decrease in the strength of correlations between followers and likes. Our decision to stick with the original dataset was due to the consistent top correlations with variables as well as the fact that the cleaned dataset missed extremes that may explain data behaviours for user engagement which may be key to understanding which metric is most valuable.
## 4. Insights from relationships in raw dataset
In this file, we conducted bivariate exploration into the top two variables - Followers & Comments - with Likes for each brand category and executed multiple kind of regression models for further analysis. This consisted of:

> - Bivariate exploration of Likes with Followers & Comments by analyzing correlation statistics
> - Multiple linear regression models using Followers & Comments against Likes for each brand category in order to find a reliable model that provides a good predictor for likes
> - Ridge & Lasso regression models to further improve on regression analyses for the 2 variables in each brand category

By constructing bivariate explorations, we learned that Followers had a much stronger correlation to Likes than Comments did, but for most brand categories, correlations were still strong for both variables, proving their worth as reliable predictors for Likes and overall, to predict post popularity. Hence we then used multiple linear regression models for each brand category to expound on this and Designer stuck out as the R^2 values were negative implying the dataset was a poor fit for the linear regression model. For the other, R^2 values explained a subtantial portion of the dataset. In order to improve these values, we executed lasso & ridge regression models which yielded similar but mostly higher values. However, from all the linear regression models, we found that Comments was a better predictor than Followers, which indicated stronger correlations did not necessarily translate to being better predictors.
## 5. Clustering
In this file, we executed a Clustering data analysis based on a K-means algorithm in order to further understad the insights we gained from our previous bivariate analysis and linear regression models. This consisted of:
> - Using Elbow method to determine number of clusters required
> - Clustering based on brand category into 2 clusters
> - Identifying distinctive features of clusters

Clustering the data under four brand categories helped us realise that even though comments have lower correlations with likes in comparison to followers, both comments and likes aligned on the same track when seen from the perspective of "user-engagement", whereas the number of followers highly indicated the "user-reach". As observed, whenever a cluster is found to have a higher number of followers, it was not necessary to see a high number of likes in that cluster. However, whenever the number of likes were high, it was seen that the number of comments received by the posts in that cluster were also high in most of the clusters under all the four brand categories. This suggested the use of comments as a better predictor when studying the variable likes in comparison to followers.

----
## Conclusion
In a nutshell, our data analysis has helped identify user engagement, particularly with respect to comments, as a more potential predictor post popularity compared to mere follower count. Regression and cluster analysis aided in proving the fact that active user interaction and engagement strongly correlates with likes. This also helped us reach the conclusion that it is indeed vital for fashion brands to come up with effective strategies that increase user engagement and not just broaden its reach. Despite the fact that this study was centered around Instagram posts and may overlook some external factors, our data analysis has helped conclude that user-engagement is a primary factor for social media success with the use of our robust data science concepts.
## Contributions
> - Hana - Insights into relationships, Video, part of EDA 
> - Sudhishna - Clustering, Anomaly Detection part of EDA 
> - Roopa - Data preparation & cleaning, Sliding, part of EDA
## Data analysis tools
> - Feature engineering (Multiple linear regression model, Lasso & Ridge regression model)
> - Correlation relationships
> - Clustering
## Our learnings
> - Clustering our datasets
> - Aggregating unique features from variables (Groupby)
> - Ridge Regression Model
> - Lasso Regression Model
> - Multiple Linear Regresssion model
> - Anomaly detection using Isolation Forests
> - Warnings library
> - Github
> - Determine viability of dataset based on outlier removal
> - Converting parts of the dataset into csv files to be used later on instead of importing the entire dataset again
## References
> 1. ChatGPT prompts: "How to reduce overfitting on linear regression models", "Understanding clustering", "Limitations of outlier removal and alternative methods to remove outliers"
> 2. https://www.geeksforgeeks.org/clustering-in-machine-learning/
> 3. https://scikit-learn.org/stable/modules/clustering.html
> 4. https://www.analyticsvidhya.com/blog/2021/09/lasso-and-ridge-regularization-a-rescuer-from-overfitting/
> 5. https://www.analyticsvidhya.com/blog/2021/07/anomaly-detection-using-isolation-forest-a-complete-guide/
