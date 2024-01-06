# EmoTrend: Sentiment-Driven Stock Market Predictions

## Overview
EmoTrend is an innovative project aimed at exploring the impact of sentiment analysis on stock market predictions. Focusing on the intricate relationship between news sentiment and stock market performance. Our study delves into sector-level and individual stock analysis, utilizing `Apache Spark MLlib` and `HDFS`.
<img width="1543" alt="image" src="https://github.com/KAIwangke/EmoTrend-Sentiment-Driven-Stock-Prediction/assets/46043861/53b40b29-8cb0-4c53-bec6-b8a8088fd415">


## Components
- `experiments`: This directory houses our experimental models, including various machine learning algorithms and statistical methods tailored for stock market prediction ultilizing Apache Spark MLlib.
- `data preparation`: Scripts and tools used for data cleaning, normalization, and transformation, ensuring quality and consistency of the dataset, ultilizing Hadoop Distributed File System (HDFS).
- `sentiment analysis`: This section is dedicated to the algorithms and processes used for extracting sentiment from large volumes of news data. It includes NLP techniques and sentiment scoring systems.

## Datasets

`GDELT Dataset`: GDELT event records are stored in an expanded version of the dyadic CAMEO format, capturing two actors and the action performed by Actor1 upon Actor2. An average “tone” score is provided for all coverage of the event, several indicators of “importance” based on media attention are provided. There are 57 columns in total in the GDELT dataset, but we will only use ‘Date’, ‘Tone’, ‘News Type’ and ‘News URL’, 4 columns in total for further analysis. There are some issues with this dataset, for example data type of ‘Date’ column is string so we should convert it into date type. Apart from this, some duplicate urls in the ‘News URL’ column also need dropping. To clean the big dataset with over 40GB, we used DataFrame in Apache Spark to efficiently obtain a reformatted dataset utilizing its scalable feature. The following picture gives a snippet of our cleaned GDELT dataset.

`HuffPost News Data`: The HuffPost news data’s schema is shown in the figure below. For sentiment analysis, we mainly adopt the columns of category, headline, date, and short description. We filter out all the news articles that do not belong to tech sectors. Then, we extract headlines and short descriptions for sentiment extraction. Before sentiment extraction, we perform a preprocessing routine that includes cleaning (removing HTML tags and special characters), normalization (converting text to lowercase), tokenization (breaking down text into words and removing stop words) and stemming and lemmatization (reducing words to their root forms). These steps are essential for ensuring the integrity and uniformity of the data, enabling more accurate and focused sentiment analysis outcomes. The HuffPost data is later then aligned with the Yahoo finance data to correlate tech sector performance with sentiment scores.


`Yahoo finance datasets`:The event driven stock price prediction have multiple different events which covering entertainment, business and technology areas, to collect the stock prices as wide as possible, as accurate as possible and also would have most high impact in the domain of each sectors, for the better conducting the time series model, and make the event driven approach more correlated. And the data source for this section we would consider Yahoo Finance, which provides a wide range of data sourcing and also has reasonable use cases and APIs.



## Methodology
The EmoTrend project employs a diverse array of data sources, including but not limited to Yahoo Finance for financial data and HuffPost/GDELT for news articles. The methodology section details our approach, which involves:
- TextBlob for accurate sentiment feature extraction from news articles.
- A combination of Linear Regression, LSTM networks, and other predictive models to analyze and forecast stock market trends.


## Findings
Our findings reveal a nuanced picture of sentiment analysis's role in stock market prediction. While the results are mixed, they highlight promising avenues for further exploration, especially in the context of individual stock analysis.
<img width="1897" alt="image" src="https://github.com/KAIwangke/EmoTrend-Sentiment-Driven-Stock-Prediction/assets/46043861/5a384c79-5c97-4429-add4-2abf3e4d4639">
<img width="1342" alt="image" src="https://github.com/KAIwangke/EmoTrend-Sentiment-Driven-Stock-Prediction/assets/46043861/f6dac718-52d3-4968-870d-3c2fcf9825d4">
<img width="1875" alt="image" src="https://github.com/KAIwangke/EmoTrend-Sentiment-Driven-Stock-Prediction/assets/46043861/a53df858-32ed-443a-bcde-84b7fda93615">

## Usage
Each directory contains detailed instructions on setup, dependencies, and execution steps for the experiments and analyses conducted in this project.

## Contributing
Contributions to EmoTrend are welcome! Please read our contributing guidelines for instructions on how to make a submission or propose enhancements.

## License
EmoTrend is made available under the MIT License.
