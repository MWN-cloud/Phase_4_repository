**MovieLens Recommendation System ReadME**

**1. Problem Statement**

In today's digital era, users find themselves inundated with an abundance of choices.
Recommender systems play a pivotal role in filtering and personalizing user
experiences. This project addresses:
1. The need for personalized movie recommendations.
2. The challenge of cold starts with new users or movies.
3. The opportunity to improve user satisfaction and business ROI through intelligent
filtering.
---
**2. Objectives**
   
i. Develop a collaborative filtering-based recommendation system.

ii. Address the cold start problem using hybrid filtering techniques.

iii. Classify movies into liked/disliked to improve filtering precision.

iv. Recommend the top 5 personalized movies for each user.

---
**3. Data Understanding**

- **Source**: MovieLens dataset (100,000 ratings)
- **Merged Shape**: (220000, ~10+)
- **Info**: Movie titles, genres, user IDs, ratings, tags, time stamps.
---
**4. Data Cleaning**
- Handled null values and dropped duplicates
- Removed ~5,000 outlier rows from the ratings data
- Normalized and cleaned inconsistent text formats
---
**5. Exploratory Data Analysis**
The dataset was explored to identify key aspects as below;

  ![image](https://github.com/user-attachments/assets/03735e2d-9306-4435-adf8-7cc9db96914d)
**Key insight: Pulp Fiction was selected for personalized filtering experiments**
![image](https://github.com/user-attachments/assets/ac9fe167-d31c-4851-92c1-eb3a0cb65585)
 **Key insight: User 68 was selected for personalized filtering experiments**
- Visuals:
- Histogram of rating distribution
- Plot: Number of Ratings vs Average Rating.
- Top 2 Most frequent tags were visualised
 --- 
**6. Prepossessing**
- Applied **Label Encoding** for classification tasks
- Applied **One-Hot Encoding** for genre data in collaborative filtering as well as matrix vectorisation
- Normalized numeric features with `MinMaxScaler`
- Utility Matrix employed to be used for collaborative filtering
![image](https://github.com/user-attachments/assets/5ac506fd-6bb2-4901-8401-4feb5fd8f5ea)
**a sparcity of 98.3% was identified on the utility matrix**
- Employed `TfidfVectorizer` to be used for content based filtering
---
**7. Modelling**
Included models:
i. Collaborative Filtering (User-Based & Item-Based) both using the utility matrix
ii. Matrix Vectorisation SVD 
ii. Content-Based Filtering - using TFidf preprocessing
iii. Hybrid Filtering (combined Content-Based + Collaborative-Based)
iv. Classification Models
- Random Forest Classifier
- Decision Tree Classifier
- Gradient Boosting Classifier
**Top classifiers** :
i. Gradient Boosting Classifier
ii. Random Forest Classifier
iii. Decision Tree Classifier
---
**8. Model Evaluation**
The following metrics were selected for evaluation;
- Precision@K
- Recall Score
- Confusion Matrix

![image](https://github.com/user-attachments/assets/f3d8a4fc-fc2b-4461-ba13-d908a3600efa)

Precision@K for the filtering models identified as the best metric for filtering
Precision also identifies as the best metric for classification

---
**9. Summary**

**Project Objectives & Outcomes**

All objectives were achieved

**1. Design a collaborative filtering based recommendation system to accurately predict
user preferences.**

This approach was applied to both user-based and item-based collaborative filtering. 
However, the cold start problem arose, necessitating the use of alternative models to address it

**2. Mitigate the cold start problem for new users and movies with limited or no ratings.**
The cold start problem was amplified by sparse user ratings. 
To address this, a hybrid model combining content-based filtering and item similarity 
proved effective by leveraging metadata over user history

**3. Develop classification models to distinguish between highly liked and disliked
movies.**
Classification models were introduced to help users discover movies outside their usual preferences. 
This approach promotes content diversity and addresses the long tail problem by recommending lesser-known, 
high-quality films.

**4. Recommend top 5 movies based on user and particular movie watched.**

Top 5 movies based on user 68 and movie 'Pulp Fiction' were;

   - Forrest Gump
   - Ferris Bueller's Day Off
   - Seven (a.k.a. Se7en)
   - Silence of the Lambs
   - The Usual Suspects

**The success factors were also achieved**:

1. The model achieved a precision@K of 0.6, meaning 3 out of 5 recommendations align with user preferences.

2. Evaluation metrics suggest recommendations align well with user preferences, though further tuning could enhance precision.

3. The system allows for easy integration of new datasets for future predictions.
   
--- 
**10. Limitations and Future Recommendations**

- Further hyperparameter tuning could have enhanced the models' performance and improved
evaluation metrics.
- The models were computationally intensive, resulting in long training times and
occasional runtime crashes due to resource constraints.
- The dataset had a limited number of movie ratings, which led to data sparsity and
impacted model effectiveness.

**Final Documents**
1. Group_6_Movie_Recommendation_System.ipynb - Final Jupyter Notebook - https://github.com/MWN-cloud/Phase_4_repository/blob/main/Group_6_Movie_Recommendation_System.ipynb
2. Group_6_Movie_Recommendation_System.pdf - Final pdf file of Jupyter Notebook -  -https://github.com/MWN-cloud/Phase_4_repository/blob/main/Group_6_Movie_Recommendation_System.pdf
3. MOVIELENS_RECOMMENDATION-SYSTEM.PPT - Non - Technical presentation - https://github.com/MWN-cloud/Phase_4_repository/blob/branch_commits/MOVIELENS-RECOMMENDATION-SYSTEM.pdf
4. Readme.md - Project Readme - https://github.com/MWN-cloud/Phase_4_repository/blob/branch_commits/README.md
5. Readme.pdf -Final pdf version of readme - [🎬 MovieLens Recommendation System README.pdf](https://github.com/user-attachments/files/19862047/MovieLens.Recommendation.System.README.pdf)
