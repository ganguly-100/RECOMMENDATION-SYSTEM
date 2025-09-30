# RECOMMENDATION-SYSTEM

*COMPANY*: CODTECH IT SOLUTIONS

*NAME*:GOPALUNI B N S K GANGULY

*INTERN ID*:CT08DZ1451

*DOMAIN*:MACHINE LEARING

*DURATION*:8 WEEKS

*MENTOR*:NEELA SANTHOSH

*DESCRIPTION*:

Project Introduction and Goal
The goal of this project was to develop a recommendation system from the ground up, a key technology for personalizing user experiences on digital platforms. The project focused on implementing a user-based collaborative filtering algorithm, a classic and effective method that generates recommendations based on the preferences of similar users. The core idea is that if a person A has the same opinion as a person B on an issue, A is more likely to have B's opinion on a different issue than that of a randomly chosen person. The entire system was built using Python, leveraging the powerful data manipulation capabilities of the Pandas library and the machine learning tools provided by scikit-learn. The final deliverable is a self-contained script that not only produces personalized movie recommendations but also includes a robust evaluation framework to measure the accuracy of its predictions.

Data Preparation and Structuring
The first step in building the recommendation engine was to prepare the data. A sample dataset was created to simulate real-world user ratings for movies, consisting of user IDs, item IDs, and corresponding ratings. This "long-format" data was then transformed into a user-item utility matrix using the Pandas pivot_table function. This matrix is the cornerstone of collaborative filtering, with users as rows, items as columns, and ratings as the values. In any real-world scenario, this matrix is inherently sparse, meaning most of its cells are empty because users typically rate only a small fraction of available items. For computational purposes, these empty cells were filled with zeros.

To properly evaluate the model's performance on unseen data, the dataset was split into a training set (80%) and a test set (20%). The training set was used to build the model—specifically, to construct the utility matrix and calculate user similarities. The test set was reserved exclusively for the final evaluation phase to provide an unbiased assessment of the model's predictive accuracy.

Core Algorithm: Similarity and Prediction
The user-based collaborative filtering algorithm was implemented in two main stages:

1. User Similarity Calculation: The system first needed to quantify how "similar" two users are based on their rating patterns. Cosine Similarity was chosen as the metric for this task. It measures the cosine of the angle between two users' rating vectors in the utility matrix. This metric is highly effective because it focuses on the orientation of the vectors rather than their magnitude, making it robust to differences in individual rating scales (e.g., one user consistently gives higher ratings than another). The result of this computation was a square user-similarity matrix, where each cell (i, j) contains a score representing the similarity between user i and user j.

2. Rating Prediction: With the similarity scores calculated, the system can predict a user's rating for an item they haven't seen before. The prediction is calculated as a weighted average of the ratings given to that item by other users, where the weights are the similarity scores of those users relative to the target user. To improve accuracy, the model accounts for user bias by first normalizing the ratings. It subtracts each user's average rating from their individual ratings before calculating the weighted average. This prevents users who tend to give universally high or low ratings from skewing the results. The final prediction is the target user's average rating plus the calculated weighted average of rating deviations from other users. This process populates the sparse utility matrix with predicted ratings.

Generating Recommendations and Evaluation
The ultimate function of the system is to provide a list of recommended items. This was achieved by using the completed matrix of predicted ratings. For any given user, the system identifies all items they have not yet rated, sorts them in descending order based on their predicted scores, and presents the top N items as the final recommendation list. This ensures the suggestions are both personalized and novel.

Finally, to validate the model's effectiveness, its performance was measured using the Mean Absolute Error (MAE). The MAE was calculated by comparing the ratings predicted by the model for the user-item pairs in the held-out test set against the actual ratings provided by the users. This metric provides a clear, interpretable measure of the average error in the model's predictions, confirming the system's viability and providing a benchmark for future improvements. A lower MAE signifies a more accurate recommendation engine.

*OUTPUT*:

<img width="1920" height="1020" alt="Sentiment Analysis with TF-IDF and Logistic Regression - Colab - Google Chrome 01-10-2025 02_03_42" src="https://github.com/user-attachments/assets/775c2426-291e-427d-bc4f-ad27dc64e708" />

<img width="1920" height="1020" alt="Sentiment Analysis with TF-IDF and Logistic Regression - Colab - Google Chrome 01-10-2025 02_03_54" src="https://github.com/user-attachments/assets/e7939f19-e87c-4ef8-8a22-b78fdfe9a584" />

