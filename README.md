# Content-Based Movie Recommender


## Goals

Given a movie name, provide a list of recommendation based on different aspect of the movies (genres, keyword, description, cast, director) using **content-based** principle.

## Data

The data is from Kaggle __[TMDB 5000 Movie Dataset](https://www.kaggle.com/datasets/tmdb/tmdb-movie-metadata)__, which contain movies up until 2017.

Here we are given 2 dataset:
* tmdb_5000_movies.csv: has metadata about the movies (genres, title, keywords, etc.)
* tmdb_5000_credits.csv: has information about the cast, crew behind the movies

## Method
Apply Content-Based principle in recommendation system

* Create item-profile consists of multiple tags from genres, keywords, production_company, actor and director
* Create a sparse matrix with each row is a movie and each column is a tag from the tag collection
* For the value in the matrix, we use 2 approaches: TF-IDF and Count(number of appearances)
* Compute similarity between movies using cosine-similarity
* Top-K movies with the highest similarity is our recommendation movies

## Results

Comparing with the recommendation list on IMDB website, we usually got about 4-5/10, which is a decent result :D

## Future Work

* Find out a more objective way to evaluate the result

* Hybrid system mixing content-based recommender and user-based collaborative filtering

* Optimize way to compute the similarity

