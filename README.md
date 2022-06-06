# RedditClassificationPosts
Classification of r/sourdough posts in flair posts 

The goal of this project is to classify reddit posts from the r/sourdough subreddit according to their Flairs. The Project can be split in 3 main steps: 
* Collecting the data
* Exploratory data analysis and Data preprocessing
* Machine Learning Application

A 30 minutes video presentation of the project can be seen here: https://drive.google.com/file/d/1_0RrY7csXMu7_UtG8Pk65-fF2Y9DVlRh/view?usp=sharing

The project is split in 10 jupyter notebook, each covering a different approach: 

0) Data Collection: 
  https://github.com/ValSauArn/RedditClassificationPosts/blob/main/00_collecting_data.ipynb
  This notebook covers the data extraction from Reddit using the PusShift API. 
    - Posts and Comments are collected on the r/sourdough subreddit on a specific period of time 
    - Both data are saved in CSV files
    
1) Data Exploration and Text Embedding:  
  https://github.com/ValSauArn/RedditClassificationPosts/blob/main/01_exploratory_data_analysis.ipynb
  This notebook covers a data exploration of both Posts and Comments datasets and displays how this exploration helps us inform our machine learning strategy. 
  It includes: 
    - Data visualisation 
    - Data preprocessing steps before vectorization of main target feature
    - Tuning of a TF-IDF vectorizer for text embedding
    - Target variable reconciliation
  The Target variable is regrouped in fewer categories to mitigate imbalances and transform numerically. 
  The data is plit between a training and a test set. The main feature of interest (all text content related to a post, including Titles, Comments and post descriptions) is transformed numerically using a TF-IDF vectorizer trained and tuned on the training set and these paramters are then used to transform the test set. The same transforned data are used for all subsequent machine learning algorithms.  
    
2) Naive Bayes Classifier: 
  https://github.com/ValSauArn/RedditClassificationPosts/blob/main/02_nb.ipynb
  In this notebook we train a Naive Bayes Classifier to predict the flair of a post. 
   
3) Logistic classification:
  https://github.com/ValSauArn/RedditClassificationPosts/blob/main/03_Logistic_regression.ipynb
  In this notebook, we train a Logistic classifier to predict the flair of a post.
 
 4) K nearest neighbours Classification:
  https://github.com/ValSauArn/RedditClassificationPosts/blob/main/04_knn.ipynb
  In this notebook, we train a KNN classifier to predict the flair of a post.
    
 5) Decision Trees:
  https://github.com/ValSauArn/RedditClassificationPosts/blob/main/05_cart.ipynb
  In this notebook, we train a decision tree classifier to predict the flair of a post.
  
 6) Random Forest
  https://github.com/ValSauArn/RedditClassificationPosts/blob/main/06_random_forest.ipynb
  In this notebook, we train a random forest classifier to predict the flair of a post. 

 7) Non Linear Support Vector Machine
  https://github.com/ValSauArn/RedditClassificationPosts/blob/main/07_svm.ipynb
  In this notebook, we train a support vector machine classifier using a rbf kernel to predict the flair of a post
  
 8) Stacking strategy: 
  https://github.com/ValSauArn/RedditClassificationPosts/blob/main/08_Stacking.ipynb
  In this notebook, we use a stacking strategy by combinimg the predictions of the previous models to predict the flair of a post: 
    - We perform a quick EDA on the probability predictions of the previous models to understand which models are worth including in the stack
    - We use a logistic regression to compute the final predictions as a linear combination of the probability predictions of the stacked models
  
 9) Summary:
 https://github.com/ValSauArn/RedditClassificationPosts/blob/main/09_Results.ipynb
 In this notebook, we collect and summarizes the predictive performances of all models. They are all compared to a base model for benchmarking. 
    
