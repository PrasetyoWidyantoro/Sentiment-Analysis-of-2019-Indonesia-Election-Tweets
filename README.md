# Sentiment Analysis of Tweets from the 2019 Indonesian Presidential Election

### Business Understanding

The sentiment analysis of tweets related to the 2019 Indonesian presidential election is crucial for understanding public opinion and gauging the political climate. By analyzing real-time reactions and opinions from tweets, we can gain insights into voter sentiments, key concerns, and trending topics. These insights are invaluable for political strategists, campaign managers, social scientists, and policymakers to make informed decisions and tailor their strategies accordingly.

### Problem Statement

Given a dataset of tweets related to the 2019 Indonesian presidential election, our objective is to build a machine learning model that can accurately predict the sentiment of each tweet. The sentiment will be classified into categories such as positive, negative, and neutral. The primary metric for evaluating the model's performance will be accuracy, chosen for its straightforward interpretation and ability to clearly measure the correctness of sentiment classification.

### Business Objective

The primary objective is to develop a robust and accurate predictive model for tweet sentiment analysis during the 2019 Indonesian presidential election. This model will aid stakeholders in making data-driven decisions regarding campaign strategies, public engagement, and communication efforts. By leveraging machine learning, we aim to:
1. Enhance the understanding of public opinion and voter sentiment.
2. Identify key issues and topics driving public discourse.
3. Enable better decision-making for political campaigns and public relations.

### Business Metrics

To ensure the success of our predictive model and its alignment with business goals, we will focus on the following metrics:
1. **Accuracy of Sentiment Classification**: The degree to which predicted sentiments align with actual sentiments.
2. **Campaign Effectiveness**: The impact of understanding voter sentiment on the effectiveness of campaign strategies and voter engagement.
3. **Public Perception**: The level of positive reception and trust among the public towards the campaign based on their responses and interactions on social media.

### Machine Learning Metrics

To evaluate and optimize our machine learning model, we will focus on the following metrics:
1. **Accuracy**: Provides a clear measure of the model's performance in classifying tweet sentiments.

### Model Development

To achieve our objective, we will develop and compare two types of models:
1. **Random Forest Classifier**: A baseline model used for its simplicity and effectiveness in handling classification tasks.
2. **Deep Learning Model (LSTM)**: Leveraging Long Short-Term Memory (LSTM) networks to capture the sequential nature of text data and improve prediction accuracy.

The next steps include data collection, preprocessing, feature extraction, model training, and evaluation. Post model evaluation, we will interpret the results, analyze feature importance, and deploy the model for real-time sentiment analysis.

## Data Definition

The dataset consists of 1815 entries, each representing a tweet related to the 2019 Indonesian presidential election. It has two columns: `sentimen` and `tweet`.

### Columns

1. **sentimen**
   - **Description**: Sentiment label for each tweet indicating the overall tone or emotion.
   - **Data Type**: `object`
   - **Unique Values**: Positive (`positif`), Negative (`negatif`), and Neutral (`netral`).

2. **tweet**
   - **Description**: Text of the tweet, reflecting opinions, reactions, or commentary related to the election.
   - **Data Type**: `object`
   - **Content**: User-generated content from Twitter, varying in length and structure.

## Data Preprocessing
1. Replace emoticons with representative text.
2. Remove URLs.
3. Remove @ from usernames, # from hashtags, punctuation, and special characters.
4. Remove numerics.
5. Remove double spaces.
6. Convert text to lower case.
7. Replace slang words with formal words.
8. Remove stopwords (excluding 'tidak' & 'semakin').
9. Perform stemming.

## Text Vectorization
1. **TFIDF**
2. **Word2Vec**
   - Skipgram
   - CBOW
3. **FastText**

## Results

### Data Stemming

#### TFIDF

| Model                          | Accuracy |
|--------------------------------|----------|
| Random Forest                  | 0.51     |
| Random Forest Tuning           | 0.59     |
| Basic MLP                      | 0.61     |
| LSTM                           | 0.54     |
| BiLSTM                         | 0.61     |

#### Word2Vec (Skipgram)

| Model                  | Accuracy |
|------------------------|----------|
| BiLSTM                 | 0.60     |
| BiLSTM (Dropout 0.3)   | 0.58     |
| GRU                    | 0.57     |

#### Word2Vec (CBOW)

| Model                  | Accuracy |
|------------------------|----------|
| LSTM                   | 0.53     |
| LSTM (Other Parameter) | 0.59     |

#### FastText

| Model                  | Accuracy |
|------------------------|----------|
| Basic MLP              | 0.60     |
| BiLSTM                 | 0.57     |
| GRU                    | 0.56     |
| LSTM                   | 0.59     |

#### BERT (Benchmark)

| Model                             | Accuracy |
|-----------------------------------|----------|
| bert-base-uncased                 | 0.63     |
| indobenchmark/indobert-base-p1    | 0.61     |
| indobenchmark/indobert-base-p1 (2 epochs) | 0.66     |

### Non-Stemming Data

| Model                           | Accuracy |
|--------------------------------|----------|
| MLP (Basic) - TFIDF            | 0.64     |
| LSTM                           | 0.62     |
| indobenchmark/indobert-base-p1 | 0.68     |

---