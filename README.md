# TextMining

I have built sentiment analysis models on the Yelp Reviews.

## Yelp Data Description

* The Yelp dataset is available in JSON files and consists of review data files and business data files for the scope of this project.
* The review data files include reviews with attributes such as review id, business id, business name, the review text, star rating, etc. 
* The Business data files include attributes such as business name, address, business id, etc.

## Data Exploration 

The sample data is in unstructured format on which I have performed analysis on the basis of three factors :
* Distribution of reviews across Star ratings
* Distribution of reviews across states
* Distribution of reviews across postal codes

I have then explored the distribution of the star ratings based on an occurrence of a particular word. 

For example, the higher star ratings have lesser usage of the word funny.
Whereas the comments regarding the word cool increase from ratings 1 to 4 with a slight drop in ratings at rating 5. 
And for the word ‘useful’ comments increase from ratings 1 to 3 and then drop from rating 3 to 5.

## Data Cleaning and Processing
* I first tokenized the words using the unnest_tokens function. Tokenizing the words retains all other attributes.
* Rare Words: These are the words that are not present in at least 10 reviews using antijoin.
* I have then removed the words containing digits(0-9), rare words, and stop words (an, a, the).
* Then, I have performed EDA on the distribution between words and stars.


### Stemming or Lemmatization?

I used lemmatization because while using dictionaries the exact words are needed for a match. Also, the root words are reduced by stemming and if used with dictionaries then we might lose on obtaining the word sentiment as the word would be removed in its root form in the original Yelp dataset after stemming.

### Term frequency, tf-idf:

* One measure of how important a word maybe is, how frequently a word occurs in a document which is called Term Frequency (TF).
* Another approach is to look at a term’s Inverse Document Frequency (IDF), which decreases the weight for commonly used words and increases the weight for words that are not used very much in a collection of documents. 
* This can be combined with term frequency to calculate a term’s TF-IDF (the two quantities multiplied together), the frequency of a term adjusted for how rarely it is used. The statistic tf-idf is intended to measure how important a word is to a document in a collection (or corpus) of documents, for example, to one novel in a collection of novels or to one website in a collection of websites.
* For building models, I have created Document Term Matrix - DTM using TF-IDF so that we can have a structured form for our text data. Rows in DTM are Reviews and Columns are words. 
![DocMatrix](https://user-images.githubusercontent.com/22790699/147393673-5561cf6b-d9a2-4d1a-a568-c7c4c9c8d696.PNG)

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

### Random Forest Model on the combined dictionary:
![rf-total](https://user-images.githubusercontent.com/22790699/147393603-636c2b39-4d86-4b1e-b5dc-a3cef921721e.PNG)

### Naive Bayes Model on the combined dictionary:
![Naivebayes-total;](https://user-images.githubusercontent.com/22790699/147393604-a2f89905-1092-430a-b058-5d5c6e5a47da.PNG)

### SVM model on the combined dictionary:
![SVM-total](https://user-images.githubusercontent.com/22790699/147393606-c5d9d66c-7649-4a1b-9dc6-4376ad620916.PNG)


## References: 
https://www.tidytextmining.com/tidytext.html
