# TextMining

I have built sentiment analsysis models on the Yelp Reviews.

## Yelp Data Description

* The Yelp dataset is available in json files and consists of review data files and business data files for the scope of this project.
* The review data files include reviews with attributes such as review id, business id, business name, the review text, star rating, etc. 
* The Business data files include attributes such as business name, address,business id,etc.

## Data Exploration 

The sample data is in unstructured format on which I have performed analysis on the basis of three factors :
* Distribution of reviews across Star ratings
* Distribution of reviews across states
* Distribution of reviews across postal codes

I have then explored the distribution of the star ratings based on an occurrence of a particular word. 

For example, the higher star ratings have lesser usage of the word funny.
Whereas the comments regarding the word cool increase from ratings 1 to 4 with a slight drop in ratings at rating 5. 
And for the word ‘useful’ comments increase from ratings 1 to 3 and then drop from rating 3 to 5.

## Data Cleaning

* Rare Words : These are the words which are not present in at least 10 reviews using antijoin.
* I have then removed the words containing digits(0-9) and stop words.

## Dictionaries used

### Bing
* The sentiment analysis divides the words as positive and negative. I have counted the total occurrences of these words in the restaurant reviews. An inner join with the sentiment dictionary word list and tokenized restaurant reviews have been taken to capture the sentiment analysis. 
* The accuracy is around 83%. The specificity is 91.59% and sensitivity is 64.90%


### NRC 
* It assigns words into one or more of the following ten categories: positive, negative, anger, anticipation, disgust, fear, joy, sadness, surprise, and trust. I have then taken the inner join with our tokenized reviews.
* The accuracy is 78.67%. And sensitivity is 63.95% and specificity is 80.96%

### AFINN
* Assigns words with a score that runs between -5 and 5, with negative scores indicating negative sentiment and positive scores indicating positive sentiment.
* The accuracy is 84.16%. The sensitivity is 70.59% and specificity is 87.99%.


## Models
