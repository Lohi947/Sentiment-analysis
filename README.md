# Sentiment-analysis
from textblob import TextBlob

# Sample restaurant reviews (you can modify or extend this list)
sample_reviews = [
    "The food was absolutely wonderful!",
    "I didn’t enjoy the meal at all.",
    "It was okay, nothing special.",
    "Amazing service and delicious pasta.",
    "The ambiance was poor and food was cold.",
    "I might visit again if improvements are made."
]

def analyze_sentiment(text):
    """
    Analyze sentiment of input text using TextBlob.
    Returns: 'Positive', 'Negative', or 'Neutral'
    """
    blob = TextBlob(text)
    polarity = blob.sentiment.polarity

    if polarity > 0:
        return "Positive"
    elif polarity < 0:
        return "Negative"
    else:
        return "Neutral"

def main():
    print("📊 Restaurant Review Sentiment Analysis Tool\n")

    for i, review in enumerate(sample_reviews, start=1):
        sentiment = analyze_sentiment(review)
        print(f"{i}. \"{review}\" -> Sentiment: {sentiment}")

    print("\n🔍 Try analyzing your own review below:")
    user_review = input("Enter your review: ")
    user_sentiment = analyze_sentiment(user_review)
    print(f"\nYour Review Sentiment: {user_sentiment}")

if __name__ == "__main__":
    main()
