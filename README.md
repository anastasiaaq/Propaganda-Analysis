# Propaganda Analysis
This repository contains an analysis of messages from russian telegram channels with propaganda. The goal of this project is to find interesting patterns, analyze viewers' reactions and engagement to different occasions, and discover the most popular bigrams/trigrams and how they changed over time.

# About Data
Main dataset has this columns: id, date, views, reactions, to_id, fwd_from, message, type, duration, dialog_id, frw_from_title, frw_from_name. Updated dataset after adding sentiment also has column sentiment_score.

1. id
  - Description: A unique identifier for each post.
  - Possible Values: Any unique number or string that identifies a message.
  - Example: 12602.0
2. date
  - Description: The timestamp when the post was made, in UTC+0.
  - Possible Values: Date and time in the format YYYY-MM-DD HH:MM:SS+00:00
  - Example: 2022-12-19 13:05:23+00:00
3. views:
  - Description: The number of views the message received.
  - Possible Values: A numeric value representing views, usually an integer or float.
  - Example: 3645.0
4. reactions:
  - Description: The list of reactions to the message, including emoji and their counts.
  - Possible Values: A list of reactions with their respective counts (e.g., 🤔: 24, 👍: 7).
  - Example: MessageReactions(results=[ReactionCount(reaction='🤔', count=24, chosen=False), 
ReactionCount(reaction='👍', count=7, chosen=False), ReactionCount(reaction='🔥', count=1, chosen=False), 
ReactionCount(reaction='😁', count=1, chosen=False), ReactionCount(reaction='🤮', count=1, chosen=False)], 
min=False, can_see_list=False, recent_reactions=[])
5. to_id:
  - Description: The ID of the recipient or group/channel the message was sent to.
  - Possible Values: A string indicating the channel ID.
  - Example: PeerChannel(channel_id=1261603870)
6. fwd_from:
  - Description: Information about the channel the post was forwarded from, if applicable.
  - Possible Values: If the message is forwarded, this field contains metadata about the original source, such as the channel ID and timestamp.
  - Example: MessageFwdHeader(date=datetime.datetime(2022, 12, 17, 9, 14, 40, tzinfo=datetime.timezone.utc), 
imported=False, from_id=PeerChannel(channel_id=1760202057), from_name=None, channel_post=4423, 
post_author=None, saved_from_peer=None, saved_from_msg_id=None, psa_type=None)
7. message:
  - Description: The content of the message.
  - Possible Values: A string containing the textual content of the message. Can include text, emojis, URLs, or media references.
  - Example: "🇵🇰🇦🇫 Исламабад сделал ставку на афганских талибов, но она не сыграла. У «Талибана» с Пакистаном по-прежнему остаются серьезные противоречия из-за так называемой линии Дюранда."
8. type:
  - Description: The type of content in the message.
  - Possible Values:
    - text (only text)
    - photo (includes an image or photo)
    - video (includes a video file)
    - audio (includes an audio file)
    - other (any media that does not fall into the above categories)
  - Example: photo
9. duration:
  - Description: The duration of the media (if applicable).
  - Possible Values: Numeric value representing the duration in seconds. If the message does not contain media, this value may be NaN.
  - Example: 103.0 (in seconds).
10. dialog_id:
  - Description: The unique identifier for the dialog or chat where the message was posted.
  - Possible Values: A string representing the dialog or chat ID, typically a user or group name.
  - Example: Abbasdjuma
11. frw_from_title:
  - Description: The title of the original sender if the message is forwarded.
  - Possible Values: The title of the sender or None if not applicable.
  - Example: None
12. frw_from_name:
  - Description: The name of the original sender if the message is forwarded.
  - Possible Values: The name of the sender or None if not applicable.
  - Example: None
13. msg_entity:
  - Description: The entity type in the message, such as hyperlinks, mentions, etc.
  - Possible Values: A string or list of entities, such as mentions (@username), hashtags (#hashtag), or links. If no special entities exist, this may be None.
  - Example: None
  
# Features
- Reactions Analysis: Adding `positive_reactions_count`/`negative_reactions_count`, `positive_reactions_percentage`/`negative_reactions_percentage` columns to messages.
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
