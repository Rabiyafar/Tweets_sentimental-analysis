Tweet Sentiment Analysis

Project Overview
This project performs sentiment analysis on tweets using the Sentiment140 dataset. The goal is to classify tweets as positive or negative, providing insights into public opinion which can be used by businesses for brand monitoring, customer feedback analysis, and trend detection.

Dataset
Source: Sentiment140 Dataset on Kaggle

Description: The dataset contains 1.6 million tweets with labels:
0 → Negative sentiment
4 → Positive sentiment

Columns:
target – sentiment label (0 = negative, 4 = positive)
id – unique tweet ID
date – date of tweet
flag – unused
user – username of the tweet author
text – content of the tweet


Preprocessing: The target column was mapped to binary labels: 0 = negative, 1 = positive.
Data Preprocessing
Text cleaning:
Removed URLs, mentions (@username), hashtags (#tag), and special characters
Converted text to lowercase
Removed stopwords using NLTK
Added a new column clean_text containing the cleaned tweet text.


Train-Test Split
Split the dataset into training (80%) and testing (20%) sets.

Features: cleaned tweet text (clean_text)
Labels: sentiment (target)

Feature Extraction
Used TF-IDF Vectorization to convert tweets into numerical features suitable for machine learning models.
Limited vocabulary to 5000 features to reduce dimensionality and improve model performance.

Modeling
Algorithm: Multinomial Naive Bayes
Reason: Effective and fast for text classification problems with TF-IDF features.

Model Evaluation
Accuracy: 0.7579 (~76%)

Classification Report:
Class	Precision	Recall	F1-Score	Support
0 (Negative)	0.75	0.77	0.76	159,494
1 (Positive)	0.76	0.75	0.76	160,506

Observations:
The model performs reasonably well with balanced precision and recall across classes.
Accuracy is ~76%, showing that the model correctly classifies most tweets.
