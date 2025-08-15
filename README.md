#Movie Recommender System

A personalized movie recommendation engine built using KNN-based collaborative filtering in Python. This project predicts and recommends movies to users based on similarity between their watched/rated movies and others’ preferences.
---
##Features

- **KNN Collaborative Filtering** — recommends movies using user–item rating similarity.  
- **User-based Similarity** — finds similar users and recommends movies they enjoyed.  
- **Interactive Interface** — powered by **Gradio** for easy, browser-based input/output.  
- **Multiple Dataset Integration** — uses ratings, movies metadata.  
- **Data Preprocessing** — handles missing values, encodes categorical features, and optimizes for recommendation speed.  
---
**Files Used:**
- `movies.csv` — Movie IDs, titles, genres  
- `ratings.csv` — User IDs, movie IDs, ratings, timestamps  
---
##Tech Stack

- **Language:** Python 
- **Libraries:**  
  - `pandas`, `numpy` — Data handling & preprocessing  
  - `scikit-learn` — KNN model for collaborative filtering  
  - `matplotlib`, `seaborn` — Data visualization  
  - `gradio` — Web-based interactive UI  
---

## Project Workflow

1. **Data Loading & Exploration**
   - Load datasets into Pandas DataFrames  
   - Check for missing values & perform cleanup  
   - Merge datasets for a unified view  

2. **Data Preprocessing**
   - Filter users & movies with sufficient ratings for better recommendations  
   - Pivot ratings into a **user–movie matrix**  
   - Fill missing ratings with `0`  

3. **Model Building (KNN Collaborative Filtering)**
   - Use **`NearestNeighbors`** from scikit-learn with cosine similarity  
   - Fit the model on the sparse user–movie matrix  

4. **Recommendation Function**
   - Accepts a movie name as input  
   - Finds similar movies using KNN neighbor search  
   - Returns the top N recommendations  

5. **Interactive Interface**
   - Integrated with **Gradio** for live input/output  
