# Stock-Prediction

This project involves using Natural Language Processing (NLP) techniques and machine learning to predict stock market movements based on daily news headlines.
Project Overview

## 1. Dataset  
The dataset consists of daily top news headlines and corresponding labels indicating whether the stock price increased (Class 1) or stayed the same/decreased (Class 0). Each day has 25 news headlines, and the task is to predict the stock market movement based on these headlines.  

## 2. Data Preprocessing  
Combining Headlines
Since each day's headlines are spread across 25 columns, they are combined into a single paragraph for each day. This step consolidates the day's news into a single text entry, which can then be used to extract features using NLP techniques and all other NLP techniques such as removing punctuation are carried out.  
  
## 3. Feature Extraction Using Bag of Words
Bag of Words (BoW): The project uses the Bag of Words model to convert the combined headlines into a numerical representation that can be used by machine learning algorithms. Specifically, the CountVectorizer from sklearn is used, with ngram_range=(2,2), which considers pairs of consecutive words (bigrams). This allows the model to capture more context from the headlines than using individual words (unigrams) alone.
The training dataset is transformed into a matrix of token counts, representing the frequency of each bigram in the news headlines.  

## 4. Model Training
Random Forest Classifier: A Random Forest classifier is used to model the relationship between the news headlines (features) and the stock market movement (label). The Random Forest is an ensemble learning method that builds multiple decision trees and combines their predictions to improve accuracy and robustness. Here, 200 trees are used (n_estimators=200), and the criterion for splitting nodes in the trees is entropy, which measures the information gain.  

## 5. Model Prediction  
The trained Random Forest model is used to predict the stock market movement on the test dataset. The test headlines are processed similarly to the training data, with the Bag of Words model transforming the text into feature vectors. 

## 6. Model Evaluation  
**Confusion Matrix:** The confusion matrix is generated to evaluate the performance of the model. It shows the number of true positives, true negatives, false positives, and false negatives, providing insight into the types of errors the model is making.  

**Classification Report:** The classification report provides precision, recall, F1-score, and support for each class (0 and 1). These metrics give a detailed overview of the model's performance in predicting each class.  

**Accuracy Score:** The overall accuracy of the model is calculated, which is the ratio of correctly predicted instances to the total instances in the test set.
