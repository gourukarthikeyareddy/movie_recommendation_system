# Movie Recommendation System

**Description**

The use case for this project is to build a recommendation system, a type of information filtering system which helps in improving the quality of search results and provides more relevant content to the user's search and history.

**Process Outline**
1. Data Collection : Collected datasets from Kaggle related to movies and the cast in those movies.

2. Data Preprocessing : Clean and preprocess the collected data to make it suitable for analysis.

3. Data Filtering : The data had been filtered into two types.
   1. Demographic Filtering - Here the movie is recommended based on its popularity and genre
   2. Content Based Filtering - Here the system used the movie metadata such as actors, genre, director


**Demographic Filtering** : In this system, we need to create a metric to rate a movie and sort the movies on the metrics. For this, we will consider IMDB's weighted rating which can be given as 

weighted rating(w) = (v/(v+m) * r) + (m/(v + m) * c)

v - number of votes for that movie

m - minimum number of required votes

r - average rating of that movie

c - mean vote across the whole report


**Content Based Filtering** : In this system, we use the content of the movie like the cast, director, and genre to find the similarity with other movies. we will first compute the Term Frequency-Inverse Document Frequency (TF-IDF) vectors for each overview. We can use the sklearn library to perform this computation. 

Term Frequency(TF) - (term instances/total instances)

Inverse Document Frequency(IDF) - log(number of documents/documents with term)


**Cosine Similarity** -  It can be used to denote the similarity between two movies. It is used as it is independent and relatively easy and faster to calculate. the tf-idf functionality in sklearn.feature_extraction.text can produce normalized vectors, in which case cosine_similarity is equivalent to linear_kernel, only slower.
so we have used linear_kernal to calculate the similarity.
