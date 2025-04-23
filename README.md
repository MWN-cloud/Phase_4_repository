**MovieLens Recommendation System ReadME**[🎬 MovieLens Recommendation System README.pdf](https://github.com/user-attachments/files/19862047/MovieLens.Recommendation.System.README.pdf)

1. Problem Statement
In today's digital era, users find themselves inundated with an abundance of choices.
Recommender systems play a pivotal role in filtering and personalizing user
experiences. This project addresses:
1. The need for personalized movie recommendations.
2. The challenge of cold starts with new users or movies.
3. The opportunity to improve user satisfaction and business ROI through intelligent
filtering.
---
2. **Objectives**
   
i. Develop a collaborative filtering-based recommendation system.

ii. Address the cold start problem using hybrid filtering techniques.

iii. Classify movies into liked/disliked to improve filtering precision.

iv. Recommend the top 5 personalized movies for each user.

---
3. Data Understanding
- **Source**: MovieLens dataset (100,000 ratings)
- **Merged Shape**: (220000, ~10+)
- **Info**: Movie titles, genres, user IDs, ratings, tags, time stamps.
---
4. Data Cleaning
- Handled null values and dropped duplicates
- Removed ~5,000 outlier rows from the ratings data
- Normalized and cleaned inconsistent text formats
---
5. Exploratory Data Analysis
- Target: Distribution of Movie-rating.
- Key insight: Pulp Fiction was selected for personalized filtering experiments
- Visuals:
- Histogram of rating distribution
- Plot: Number of Ratings vs Average Rating.
---
6. Data Cleaning
   
i. Handling null values

ii. Dropping duplicates

iii. Display and Clean Outlier

8. Exploratory Data Analysis
- Distribution of movie Rating as visual (PULP fiction was selected as one of the
input for the filtering models.
- Number of Ratings vs Average Rating visual
8. Prepossessing
- Applied **Label Encoding** for classification tasks
- Applied **One-Hot Encoding** for genre data in collaborative filtering
- Normalized numeric features with `MinMaxScaler`
---
9. Utility Matrix
- Constructed User-Movie matrix
- Employed `TfidfVectorizer` in conjunction with `cosine_similarity` to assess content
similarity.
- Applied Truncated SVD for dimensionality reduction
---
10. Modelling
Included models:
i. Collaborative Filtering (Memory-Based & Model-Based)
ii. Content-Based Filtering
iii. Hybrid Filtering (combined content + collaborative)
iv. Classification Models
- Random Forest Classifier
- Decision Tree Classifier
- Gradient Boosting Classifier
---
11. Classification
**Top classifiers** :
i. Gradient Boosting Classifier
ii. Random Forest Classifier
iii. Decision Tree Classifier
---
12. Model Evaluation
- Precision@K
- Recall Score
- Confusion Matrix
-**RMSE** for regression-based recommendation scoring
---
**Summary**
Project Objectives & Outcomes
1. Design a collaborative filtering based recommendation system to accurately predict
user preferences.
We implemented both user-based and item-based collaborative filtering techniques.
While they showed potential, we observed that integrating content-based filtering or
building a hybrid model significantly improved precision. One key challenge was the
cold start problem, which hindered performance when ratings were sparse.
---
3. Mitigate the cold start problem for new users and movies with limited or no ratings.
The cold start problem was particularly pronounced due to the limited number of user
ratings. To mitigate this issue, we integrated content-based filtering and item
similarity methodologies, which depend on metadata rather than user history. The
hybrid model—an amalgamation of collaborative and content-based approaches—
demonstrated remarkable efficacy in alleviating cold start scenarios.

5. Develop classification models to distinguish between highly liked and disliked
movies.
By introducing classification models, we provided a mechanism for users to explore
movies beyond their usual preferences. These models help uncover hidden gems and
challenge user biases, potentially increasing their exposure to a broader variety of
content. This strategy also helps address the long tail problem by recommending
lesser-known but highly rated movies.

7. Recommend top 5 movies based on user and particular movie watched.
Top 5 movies based on user 68 and movie 'Pulp Fiction' were;
   -Forrest Gump
   -Ferris Bueller's Day Off
   -Seven (a.k.a. Se7en)
   -Silence of the Lambs
   -The Usual Suspects

**The success factors were also achieved**:
1. Model Performance: Achieve a high precision@K > 0.6 for accurate recommndation to
the users
A high precision was achieved of 0.6 which will now have 3 out of 5 movies recommended
as per the user preference.
2. User Satisfaction: Recommendations should align with user preferences as evaluated
via user feedback or online metrics
From the metrics output the comparison between the models outcome and the actual user
preference indicates that users will be satisfied however more tuning of the models
needs to be done to increase precision
3. There is provision to include new datasets for prediction

**Limitations and Future Recommendations**

Further hyperparameter tuning could have enhanced the models' performance and improved
evaluation metrics.
The models were computationally intensive, resulting in long training times and
occasional runtime crashes due to resource constraints.
The dataset had a limited number of movie ratings, which led to data sparsity and
impacted model effectiveness.
