# Module 4 Final Project

## Objective

Create a recommendation system that will make movie recommendations for new users using datasets from [MovieLens](https://grouplens.org/datasets/movielens/latest/).


## The Datasets

The MovieLens database contains two datasets that were used for the project. 

![movies.csv](movies.csv): containing the movie id, title and genres for 9,742 unique movies. 



![ratings.csv](ratings.csv): containing the user id, movie id, rating and timestamp for 100,836 movie ratings. 




## Data Analysis

![](images/movie_count_per_genre.png)

![](images/average_rating_per_genre.png)

![](images/ratings_boxplot_by_genre.png)

![](images/most_frequently_rated_movies.png)

![](images/movie_count_per_rating.png)


## Method

### memory based/neighborhood based collaborative filtering:

With neighborhood-based collaborative filtering methods, you're attempting to quantify just how similar users and items are to one another and getting the top N recommendations based on that similarity metric.

Cross validating with KNNBasic: A basic collaborative filtering algorithm
Cross validating with KNNBaseline: A basic collaborative filtering algorithm taking into account a baseline rating.
Cross validating with KNNWithMeans: A basic collaborative filtering algorithm, taking into account the mean ratings of each user.
Cross validating with KNNWithZScore: A basic collaborative filtering algorithm, taking into account the z-score normalization of each user.

Parameter grid for KNN: 
Similarity metrics: 
    *pearson: Calculate Pearson correlation coefficients between all user (or item) pairs. 
    *consine: Calculate cosine similarity between all user (or item) pairs. 
    *MSD: Calculates the mean squared difference between similarity between all users. 
    *Item-based: measures the similarity between the items that target users rates/interacts with and other items 
    *User-based: measures the similarity between target users and other users

### model based collaborative filtering: 

Singular-Value Decomposition or SVD is a common and widely used matrix decomposition method. All matrices are able to be factored using an SVD, which makes it more stable than other methods, such as the eigendecomposition.

With Singular-Vale Decomposition, or SVD, the recommendation problem is turned into an optimization problem that deals with how good we are in predicting the rating for items given a user. Two common metrics to score the optimization are Root Mean Square Error, RMSE, and Mean Absolute Error, MAE. The lower the value for each of the scoring metrics, the better the model performed.

Alternating least squares is another matrix decomposition method, but it is best used when there are missing values in the matrix. Because our dataset does not contain missing values, we will stick to SVD for matrix decomposition. 

Parameter grid for SVD: 
    *n_epochs: the number of iterations of SGD, which is basically an iterative method used in Statistics to minimize a function.
    *lr_all: the learning rate for all parameters, which is a parameter that decides how much the parameters are adjusted in each iteration.
    *reg_all: the regularization term for all parameters, which is a penalty term added to prevent overfitting.
    
### scoring

Mean Absolute Error (MAE) computes the deviation between predicted ratings and actual ratings

Root Mean Square Error (RMSE) is similar to MAE, but places more emphasis on larger deviation (punishes gross inaccuracies)

## Findings

## Table of Contents

[Jupyter_Notebook](RecSystem.ipynb)

[Summary_Slides]()

[Blog_Post](https://medium.com/@stacyshingleton/movie-recommendations-65aa0566215c)
