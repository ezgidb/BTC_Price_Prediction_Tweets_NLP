# BTC Price Prediction with Tweets' Sentiment Analysis
- BtcUsdt Price Prediction Based on Twitter Messages Sentiment Analysis Model Development

## Objective:
 - BTC price prediction based on tweets' sentimental scores and develop trade strategies

## Data:
**Twitter Dataset :** https://www.kaggle.com/datasets/kaushiksuresh147/bitcoin-tweets?select=Bitcoin_tweets_dataset_2.csv 

**BTCUSDT Hourly Historical Data :** Binance API (* Binance_Scraper.ipynb)

## Methodology:
### 1. Preprocessing : Cleaning & Text Normalization for NLP:
- 1.1 Lovercase whole tweets Cleaning :

  - remove emojis
  - remove links
  - remove hashtag sign
  - remove 3dots
  - remove "rt @"
  - remove mentiones
  - remove "rt &"data = re.sub(rt_and_patters," ",str(data))
  - remove "\n"
  - fix contractions Can't = cannot
  - remove punctuations
  - remove digits

- 1.2 Tokenization & Text Normalizations:

  - Word Tokens
  - Stemming
  - Lemmatization
  - Remove Stopwords


### 2. Feature Creation:

  - Calculated houry tweet volume database
  - BTC historical data merging
  
### 3 Sentiment Analysis by TextBlob:
  - Subjectivity Score
  - Polarity Score
  - Created Sentimens (Positive/Neutral/Negative)
  - Calculated Sentiment scores with Subjectivity, tweet volume

### 4. Explorative Data Analysis:
  
  - Checking for Null values
  - Checking for outliers
  - Chacking for cross corralation
### 5. Feature Importance:
   **Sklearn Libraries**
  - Mutual_info_regression
  - F_regression
  - Random Forest Feature Importance
  - RFE(Random Forest )
  
### 6. Processed Final Data for Machine Learning:
Timeseries DataFrame with selected features Processed data is trained with random forest regression model and cross validated with Random Grid Search and Grid Search methodologies for tuning.

- ### Methodology:

### 1. Random Forest Estimator
    - Multiple Feature
    - Sentiment Score
    - Model Evauation

### 2. Random Grid Saerch
    - Get best params
    - Model Evaluation
    - Grid Search
    - Use Random Search best params
    - Get Best params
    - Model Evaluation
    
## Conclusion : 
After evaluating with different paramaters, accuracy rates didn't increas significantly. On the other hand, when same dataframe is trained based on only "sentiment_score" feature, gives much more accuracy rate.

| **Model**  | **Accuracy** |
| ------------- | ------------- |
| Full data simple RFG  | %86.651112  |
| Full data RFG + RB  | %86.687147  |
| Full data RFG+RB+GS  | %86.704498  |
| Single Feature RFG  | %95.930713  |
| Single Feature RFG+RB  | %95.935596  |


## Further Study :

  - Text Normalization with bag of word specific for cryptocurrency
  - Bigger size of twitter data
  - Further LSTM(Long short-term memory) sentiment analysis.
  - Real data set validation
