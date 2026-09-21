# DSA 4060 Week 1 Popularity Recommender

## Student

- Name: TODO
- Student number: TODO

## Project overview

This project explores MovieLens user-item ratings and builds two non-personalized movie recommendation baselines: a minimum-rating popularity recommender and a weighted-rating recommender.

## Dataset

The project uses the MovieLens `latest-small` dataset from GroupLens:

- Source: https://grouplens.org/datasets/movielens/latest/
- Files used: `movies.csv` and `ratings.csv`
- Date accessed: 2026-09-21

The dataset zip is stored in `data/ml-latest-small.zip` for local reproducibility. The notebook extracts it into `data/ml-latest-small/` when needed.

## Methods

1. Rating-count and average-rating exploration
2. Minimum-rating popularity baseline
3. Weighted-rating baseline
4. Method comparison, visualization, and basic output checks

## How to run

1. Clone the repository.
2. Install packages: `pip install -r requirements.txt`
3. Open `notebooks/week1_popularity_recommender.ipynb`.
4. Run all cells from top to bottom.

## Key findings

The dataset contains 610 users, 9,742 movies, and 100,836 ratings. Only about 1.7% of possible user-movie pairs have ratings, so the rating matrix is very sparse.

`Forrest Gump (1994)` received the most ratings with 329 ratings and an average rating of 4.16. Under the minimum-50-ratings method, `Shawshank Redemption, The (1994)` ranked first with 317 ratings and an average rating of 4.43. The weighted-rating method also ranked `Shawshank Redemption, The (1994)` first, with a weighted score of 4.34.

The two Top 10 lists overlap on three titles: `Fight Club (1999)`, `Godfather, The (1972)`, and `Shawshank Redemption, The (1994)`. The weighted method is more conservative because it uses the 90th-percentile rating-count threshold and pulls each score toward the overall average.

## Limitations

The recommendations are not personalized because every user receives the same ranked list. The approach can reinforce popularity bias, gives limited exposure to new or niche movies, and cannot explain why users liked a movie. New movies with no ratings also face a cold-start problem.

## Repository structure

```text
.
├── data/
│   └── ml-latest-small.zip
├── images/
│   └── top10_recommendations.png
├── notebooks/
│   └── week1_popularity_recommender.ipynb
├── .gitignore
├── README.md
└── requirements.txt
```

## Screenshot

![Top 10 recommendations](images/top10_recommendations.png)
