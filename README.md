# Movie Recommendation System


## Goals

Given a movie name, provide a list of recommendation based on different aspect of the movies (genres, keyword, description, cast, director) using **content-based (CB), collaborative-filtering (CF)** principle.

## Data

### For CB_Recommender:

The data is from Kaggle __[TMDB 5000 Movie Dataset](https://www.kaggle.com/datasets/tmdb/tmdb-movie-metadata)__, which contain movies up until 2017.

Here we are given 2 files:
* tmdb_5000_movies.csv: has metadata about the movies (genres, title, keywords, etc.)
* tmdb_5000_credits.csv: has information about the cast, crew behind the movies

### For CF_Recommender:

The data is from [MovieLens DataSet](https://grouplens.org/datasets/movielens/). This version of the dataset ([1M](https://grouplens.org/datasets/movielens/1m/)) contains 1,000,209 anonymous ratings of approximately 3,900 movies made by 6,040 MovieLens users who joined MovieLens in 2000.

There are 3 files:

* movies.csv
* users.csv
* ratings.csv


## Method
Apply Content-Based principle in recommendation system

* Create item-profile consists of multiple tags from genres, keywords, production_company, actor and director
* Create a sparse matrix with each row is a movie and each column is a tag from the tag collection
* For the value in the matrix, we use 2 approaches: TF-IDF and Count(number of appearances)
* Compute similarity between movies using cosine-similarity
* Top-K movies with the highest similarity is our recommendation movies

Apply Collaborative-Filtering principle in recommendation system:

* Use **Dimensionality Reduction** technique in recommendation system, this is also known as low-rank-matrix factorization
* Use **surprise** package for implementation

## Results

### For CB_Recommender:

Comparing with the recommendation list on IMDB website, we usually got about 4-5/10, which is a decent result :D

### For CF_Recommender:

Get a RMSE of 0.874, which is a decent score

## Future Work


* Hybrid system mixing content-based recommender and user-based collaborative filtering

* Optimize way to compute the similarity

