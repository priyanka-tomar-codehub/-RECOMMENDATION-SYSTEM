# -RECOMMENDATION-SYSTEM
COMPANY:CODTECH IT SOLUTIONS NAME:PRIYANKA TOMAR INTERN ID:CT04DY481 DOMAIN:MACHINE LEARNING DURATION:4 WEEKS MENTOR:NEELA SANTOSH
Movie Recommendation System using Collaborative Filtering (SVD with Sparse Matrices)
🔹 Introduction

Recommendation systems are widely used in platforms like Netflix, Amazon, and YouTube to suggest personalized content to users.
This project builds a memory-efficient recommendation system using Collaborative Filtering with Matrix Factorization (SVD) on the MovieLens dataset.

🔹 Dataset

Ratings file: Contains userId, movieId, and rating (explicit feedback from users).

Movies file: Contains movieId and title (movie metadata).
The dataset contains over 1 million ratings, so efficiency is important.

🔹 Methodology

Data Preprocessing

User and Movie IDs are mapped to continuous indices.

A sparse user–item rating matrix is created (csr_matrix) to save memory.

Matrix Factorization with SVD

Instead of converting the full matrix into dense form (which causes MemoryError), we use Truncated SVD (svds from SciPy).

The rating matrix is demeaned per user before factorization.

The decomposed matrices U, Σ, and Vt capture hidden relationships between users and movies.

Prediction

Predicted ratings are reconstructed as:

R_hat = U × Σ × Vt + user_mean


Predictions are used to recommend movies a user has not yet rated.

Evaluation Metrics

RMSE (Root Mean Squared Error) and MAE (Mean Absolute Error) are calculated on a test sample of ratings.

These metrics check how close the predictions are to actual ratings.

Top-N Recommendations

For a given user, movies already rated are filtered out.

The system ranks the remaining movies by predicted rating and recommends the Top-N.

Visualization

A bar chart is generated showing the predicted ratings of recommended movies for a sample user.

Export Results

Recommendations are also saved to sample_recommendations.csv for inspection.

🔹 Results

The model successfully generates personalized Top-10 movie recommendations for any user.

Example: For User 1, the system outputs a ranked list of movies with predicted ratings.

RMSE is typically in the range 0.85–0.95 (depending on dataset size and SVD components k).

🔹 Conclusion

Collaborative Filtering using SVD with sparse matrices provides a scalable solution for large datasets (1M+ ratings).

The system is memory-efficient, accurate, and demonstrates the core working of recommendation engines.

This framework can be extended by adding implicit feedback, content-based filtering, or hybrid models for improved accuracy.

