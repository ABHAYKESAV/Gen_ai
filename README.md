import nltk
from nltk.sentiment import SentimentIntensityAnalyzer
 
# Download NLTK resources (if not already downloaded)
nltk.download('vader_lexicon')
 
# Initialize the sentiment analyzer
sid = SentimentIntensityAnalyzer()
 
# Input text
text = input("Enter your text: ")
 
# Analyze sentiment for the input text
sentiment_scores = sid.polarity_scores(text)
 
# Classify emotions based on sentiment scores and assign emojis
if sentiment_scores['compound'] >= 0.05:
    emotion = '��� Positive'
elif sentiment_scores['compound'] <= -0.05:
    emotion = '��� Negative'
else:
    emotion = '��� Neutral'
 
print(f"Text: {text} | Emotion: {emotion}")
