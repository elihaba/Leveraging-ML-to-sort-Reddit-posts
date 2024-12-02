# Improving Reddit Moderation with Machine Learning

### Overview

Reddit moderators face significany challenges in managing content across communities. One area machine learning could make this task easier is identifying misclassified content. This is particularly true for subreddits with overlapping topics, such as r/NFL and r/CFB. Despite their focus on professional and college football, respectively, these subreddits often share content, particularly around events like the NFL Draft, which can potentially lead to misclassified posts. The goal of this project is to develop a machine learning model to automatically classify posts into the correct subreddit, reducing manual moderation efforts and improving both content management and user experience.

---

## Table of Contents
1. [Data](#Data)
2. [Requirements](#Requirements) 
3. [Executive Summary](#Executive-summary)

---

## Data
Data Source (Reddit)

- [NFL](../datasets/nfl.csv)
- [CFB](../datasets/cfb.csv)
- [Merged Posts](../datasets/merged_posts.csv)


---

## Requirements

- A programming environment such as Jupyter Lab
- pandas
- numpy
- PRAW
- matplotlib.pyplot
- scikit-learn
- seaborn
- WordCloud

---

## Executive Summary
The moderators of Reddit’s r/NFL and r/CFB are facing increasing challenges in managing content within their communities. Both subreddits cover distinct aspects of football — with r/NFL focused on professional football and r/CFB on college football — but there is significant overlap in content. Posts related to college players entering the NFL, for example, can belong to either subreddit, leading to misclassification. This results in an increased workload for moderators, who must manually relocate misplaced content, which can affect the quality of user engagement and disrupt the flow of relevant discussions.

To address this challenge, a machine learning model has been developed to automatically classify Reddit posts into the appropriate subreddit. By leveraging natural language processing techniques, the model aims to streamline the moderation process by reducing the time and effort spent on manually sorting posts. The goal is not to analyze broader community trends, but to optimize content classification, ensuring that posts are accurately categorized and improving subreddit management. This will enhance the user experience, reduce moderator workload, and contribute to a more organized and efficient community.



#### Purpose

The purpose of this project is to create a machine learning model that automatically classifies Reddit posts into the correct subreddit, r/NFL or r/CFB, by analyzing post content. The primary goal is to build a model that achieves sufficient accuracy to ultimately be depoloyed. By applying natural language processing techniques, the model will streamline subreddit management, improve user experience, and foster better community engagement.
  
#### Methods
The first step in this project involved gathering over 2,000 posts from each of the r/NFL and r/CFB subreddits using the Python Reddit API Wrapper (PRAW). These posts were collected to build a representative set for models to train on. Each post was labeled according to the subreddit it originated from, providing the target variable for classification. The dataset was then pre-processed to remove irrelevant content such as  stop words to ensure clean, usable data.

The cleaned text was then transformed into numerical data using Count Vectorization, which converts the text into a sparse matrix of token counts. This transformation captures the frequency of words within each post, allowing the machine learning models to analyze and classify the posts based on their content.

Several machine learning models were applied to the data to classify the posts into their respective subreddits: Naive Bayes, Logistic Regression, Support Vector Machines (SVM), and Random Forests. These models were trained and evaluated using cross-validation, and the accuracy was calculated for each classifier. After testing the models on a separate testing dataset, the Naive Bayes model was found to outperform the others, achieving an accuracy of 96% on the testing data. Given its strong performance, computational advantages, and scalability Naive Bayes was selected as the final model for the classification task.

#### Findings
The findings from this project revealed that the Naive Bayes model outperformed other classifiers, achieving 96% accuracy on testing data, making it the most effective solution for automatically classifying Reddit posts between r/NFL and r/CFB.

#### Next Steps
Next steps involve refining the Naive Bayes model by incorporating user feedback to further enhance its accuracy and adaptability. Additionally, the model can be scaled to classify posts across other subreddit pairs, broadening its application for content moderation across Reddit. Future improvements could also include integrating more features, such as sentiment analysis, to better capture the context of posts and improve classification performance.