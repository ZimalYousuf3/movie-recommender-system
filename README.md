# Movie Recommender System (Content + Collaborative + Hybrid)

A movie recommendation engine built on the MovieLens (ml-latest-small) dataset, exploring three different recommendation strategies and combining them into a single hybrid model.

## Workflow

- Loaded and explored `movies.csv` and `ratings.csv`, checked for missing values
- Merged movies and ratings into a combined dataframe for collaborative analysis
- **Content Based Filtering** — vectorized movie genres using `TfidfVectorizer`, and used `cosine_similarity` to recommend movies with similar genre profiles
- **Collaborative Filtering** — built a user-item rating matrix, transposed it into a movie-user matrix, and used `cosine_similarity` to recommend movies rated similarly by the same users
- **Hybrid Recommender** — combined both content and collaborative similarity scores using weighted averages, safely aligning the two differently-sized similarity tables using `reindex()` and `fillna(0)`

## Example Output (for "Toy Story (1995)")

| Method | Top Recommendations |
|---|---|
| Content Based | Antz, Toy Story 2, The Adventures of Rocky and Bullwinkle |
| Collaborative | Toy Story 2, Jurassic Park, Independence Day |
| Hybrid | Toy Story 2, Monsters Inc., Shrek |

## Tools & Libraries Used

- Python
- Pandas
- NumPy
- Scikit-learn (`TfidfVectorizer`, `cosine_similarity`)

## Dataset

[MovieLens (ml-latest-small)](https://grouplens.org/datasets/movielens/latest/) from GroupLens, containing 9,742 movies and 100,836 ratings from 610 users.
