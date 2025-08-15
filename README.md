# Movie Recommender System

A personalized movie recommendation engine built using KNN-based collaborative filtering in Python. This project predicts and recommends movies to users based on similarity between their watched/rated movies and others’ preferences.
---
## Features

- **KNN Collaborative Filtering** — recommends movies using user–item rating similarity.  
- **User-based Similarity** — finds similar users and recommends movies they enjoyed.  
- **Interactive Interface** — powered by **Gradio** for easy, browser-based input/output.  
- **Multiple Dataset Integration** — uses ratings, movies metadata.  
- **Data Preprocessing** — handles missing values, encodes categorical features, and optimizes for recommendation speed.  
---
## Files Used:
- `movies.csv` — Movie IDs, titles, genres  
- `ratings.csv` — User IDs, movie IDs, ratings, timestamps  
---
## Tech Stack

- **Language:** Python 
- **Libraries:**  
  - `pandas`, `numpy` — Data handling & preprocessing  
  - `scikit-learn` — KNN model for collaborative filtering  
  - `matplotlib`, `seaborn` — Data visualization  
  - `gradio` — Web-based interactive UI  
---

## Project Workflow

### 1. Data Loading & Exploration
- Imported the MovieLens datasets (`movies.csv`, `ratings.csv`) into Pandas DataFrames.  
- Checked for any missing or inconsistent values and handled them where necessary.  
- Merged the datasets so each rating record also included movie titles and genres for easier reference later.  

### 2. Data Preprocessing
- Removed users and movies with very few ratings to avoid poor recommendations.  
- Transformed the data into a **user–movie matrix** where rows represent movies and columns represent users.  
- Filled unrated movie entries with `0` to create a complete matrix for similarity calculations.  

### 3. Model Building (KNN Collaborative Filtering)
- Used scikit-learn’s **`NearestNeighbors`** model with cosine similarity as the metric.  
- Trained the model on the sparse user–movie rating matrix so it could find similar movies efficiently.  

### 4. Recommendation Function
- Wrote a custom Python function that takes a movie title as input.  
- Finds the corresponding row in the matrix and uses the trained KNN model to get the closest matches.  
- Returns the top N most similar movies along with their similarity scores.  

### 5. Interactive Interface
- Integrated the recommendation function with **Gradio** to create a simple, interactive web app.  
- The app takes a movie title in a text box and instantly displays a list of similar movies right in the browser.  
