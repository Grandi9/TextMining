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

Rare Words : These are the words which are not present in at least 10 reviews using antijoin.

I have then removed the words containing digits(0-9) and stop words.

