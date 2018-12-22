# Sentiment Analysis of Amazon Fine Food reviews
### Learning Project
## 1.Business Problem
### 1.1 Description
#### Description
This dataset consists of reviews of fine foods from amazon. The data span a period of more than 10 years, including all ~500,000 reviews up to October 2012. Reviews include product and user information, ratings, and a plain text review. It also includes reviews from all other Amazon categories.

#### Problem Statemtent
Given a review, determine whether the review is positive (Rating of 4 or 5) or negative (rating of 1 or 2).

### 1.2 Source
https://www.kaggle.com/snap/amazon-fine-food-reviews

## 2.Machine learning problem
### 2.1 Data
#### 2.1.1 Data Overview
Number of reviews: 568,454
Number of users: 256,059
Number of products: 74,258
Timespan: Oct 1999 - Oct 2012
Number of Attributes/Columns in data: 10

Attribute Information:

1.Id
2.ProductId - unique identifier for the product
3.UserId - unqiue identifier for the user
4.ProfileName
5.HelpfulnessNumerator - number of users who found the review helpful
6.HelpfulnessDenominator - number of users who indicated whether they found the review helpful or not
7.Score - rating between 1 and 5
8.Time - timestamp for the review
9.Summary - brief summary of the review
10.Text - text of the review

### 2.2 Mapping the real-world problem to a Machine Learning Problem
#### 2.2.1 Type of Machine Learning Problem
Binary Classification problem,Given a review we need to predict it is negative or postive reviews
#### 2.2.2 Performance metric
F1-score

## 3.Data Preprocessing
* Remove Special characters 
* Remove stop words
* Remove HTML Tags
* Removing null coloumn
## 4.Splitting Data
### Time based Splitting into train,cv and test
    Train-60
    cv-20
    test-20
    
## Applying various Machine Learning models
### 1-KNearestNeighbour
#### 1.1-Knn BruteForce
##### Conclusion
| Model | hyper parameter   |F1-score  TEST|Accuracy score TEST
|------|------|------|------|
|  unigram  | 15| 83.7%|0.50|
| Bi-gram | 15| 83.5%|0.48|
|  Tf-IDF | 15| 84.8%|0.574|
| Av-Word2Vec |17|86.9%|0.689|
|  Tf-IDF Word2vec | 17|86.1%|0.656|

#### 1.2-Knn KdTree
##### Conclusion
| Model | hyper parameter   |F1-score  TEST|Accuracy score TEST
|------|------|------|------|
|  unigram  | 7| 0.534|83.858%|
| Bi-gram | 9| 0.492|0.492%|
|  Tf-IDF | 11| 0.574|84.808%|
| Av-Word2Vec |11|0.687|86.475%|
|  Tf-IDF Word2vec | 17|0.646|85.458%|

### 2.Naive Bayes
##### Conclusion
| Model | hyper parameter   |F1score test|accuracy Test
|------|------|------|------|
|  unigram  |0.01| 0.818|90.17%|
| Bi-gram | 0.5|0.81|91.172%|
|  Tf-IDF | 0.05| 0.733|89.055%|

### 3.Logistic Regression
#### L1 regulization
#### Conclusion
| Model | hyper parameter   |F1score test|accuracy Test
|------|------|------|------|
|  unigram  | 1| 0.793|87.740%|
| Bi-gram | 1|0.812| 90.650%|
|  Tf-IDF | 1| 0.826| 91.260%|
| Av-Word2Vec |100|0.777|88.565%|
|  Tf-IDF Word2vec |0.0001|0.607| 84.705%|

#### L2 regulization
#### Conclusion

| Model | hyper parameter   |F1score test|accuracy Test
|------|------|------|------|
|  unigram  | 0.0001| 0.777|86.7%|
| Bi-gram | 1|0.692|87.210%|
|  Tf-IDF | 10000| 0.87|92.715%|
| Av-Word2Vec |100|0.72|88.7%|
|  Tf-IDF Word2vec | 100|0.732|86.917%|

### 4.Decision Tree
#### Conclusion
| Model | hyper parameter   |F1score test|accuracy Test
|------|------|------|------|
|  unigram  | 43| 0.700|84.665%|
| Bi-gram | 75|0.723| 85.275%|
|  Tf-IDF | 53| 0.717| 84.600%|
| Av-Word2Vec |7|0.680|84.75%|
|  Tf-IDF Word2vec |9|0.656| 83.66%|

### 5.GBDT
#### Conclusion
|Model|learning Rate|n_estimator|F1score test|accuracy Test
|-----|-------------|-----------|------------|-------------|
|unigram|0.1|500|0.786|89.595%|
|Bi-gram|1|500|0.804|89.580%|
|Tf-IDF|0.5|500||0.812|90.055%|
|Av-Word2Vec|0.5|60|0.777|88.390%|
|Tf-IDF Word2vec|0.1|500|0.746|87.745%|


### 6.RandomForest
#### Conclusion
|Model|Max-Depth|n_estimator|F1score test|Accuracy Test
|-----|---------|-----------|------------|-------------|
|unigram|150|12|0.713|87.030%|
|Bi-gram|140|4|0.566|83.510%|
|Tf-IDF|150|4|0.636|84.35%|
|Av-Word2Vec|70|16|0.461|82.305%|
|Tf-IDF Word2vec|20|12|0.559|54.115%|

## Conclusion


