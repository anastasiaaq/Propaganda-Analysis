# Propaganda Analysis
This repository contains an analysis of messages from russian telegram channels with propaganda. The goal of this project is to find interesting patterns, analyze viewers' reactions and engagement to different occasions, and discover the most popular bigrams/trigrams and how they changed over time.

# Features
- Reactions Analysis: Adding `positive_reactions_count`/`negative_reactions_count`, `positive_reactions_percentage`/negative_reactions_percentage` columns to messages.
- Text Processing: Text is processed using nltk library, which helps to find the most common bigrams, trigrams, and words that occur in the same sentence with a certain word, before and after certain words.
- Sentiment Analysis: Every message's sentiment is defined using [kartaslovsent](https://github.com/dkulagin/kartaslov/tree/master/dataset/kartaslovsent).
- Data Visualization: The analysis results are visualized using matplotlib and WordCloud for easy interpretation of trends, word frequencies, and reaction dependencies.

# Libraries Used
- pandas
- matplotlib
- nltk
- wordcloud
- re

# Purpose
This project aims to analyze the content and patterns within messages shared in russian telegram channels. By identifying key themes, trends, and sentiment in the messages, the goal is to gain a deeper understanding of the language, techniques (e.g. using hyperbolic language), and topics that dominate these discussions. The insights generated will help identify russian's reaction to propaganda and provide a clearer view of the kinds of messages being communicated within these channels over time. It can be used to counter disinformation and get more proof and data to analyse about the oppression of Ukrainians.
