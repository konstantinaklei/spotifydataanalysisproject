# Spotify Data Analysis & Recommendation System 🎵

This project explores the Spotify Tracks Dataset using **Exploratory Data Analysis (EDA)**, **Unsupervised Learning (K-Means Clustering)**, and **Content-Based Filtering** to build a comprehensive music recommendation engine.

---

## 🚀 Overview
The goal of this project is to analyze the audio characteristics of songs (such as danceability, energy, and valence) to understand musical trends and create an automated system that suggests similar songs based on their "mood" and technical profile.

## 🛠️ Data Pipeline & Process

### 1. Data Cleaning & Preprocessing
* **Handling Missing Values:** Dropped rows with null values to ensure data integrity.
* **Duplicate Removal:** Removed duplicate `track_id` entries to ensure each song is unique in the analysis.
* **Filtering:** Removed tracks shorter than 10 seconds (10,000 ms) to exclude non-song entries or noise.
* **Feature Scaling:** Used `MinMaxScaler` to normalize audio features to a $[0, 1]$ range for fair comparison between features like `tempo` and `energy`.

### 2. Exploratory Data Analysis (EDA)
* **Genre Analysis:** Visualized the distribution of danceability across genres using **Box Plots** and **Scatter Plots**.
* **3D Visualization:** Explored the relationship between `Energy`, `Danceability`, and `Popularity` in a interactive 3D space.
* **Radar Charts:** Created "musical fingerprints" for top genres by comparing their average audio feature scores.

### 3. Machine Learning: Mood Clustering
* **Optimal K-Selection:** Used the **Elbow Method** and **Silhouette Score** to determine that $K=4$ is the optimal number of clusters.
* **K-Means Clustering:** Categorized the dataset into 4 distinct "Moods":
    * ⚡ **High-Energy Party:** High danceability, energy, and tempo.
    * 🌑 **Dark & Intense:** High energy/loudness but very low valence (intense/dark mood).
    * 🌙 **Chill & Acoustic:** High acousticness with lower energy and loudness.
    * 🧠 **Deep Focus / Instrumental:** High instrumentalness and minimal speechiness.
* **Dimensionality Reduction:** Applied **PCA (Principal Component Analysis)** to visualize high-dimensional audio data in a 2D scatter plot.

### 4. Content-Based Recommendation Engine
* **Cosine Similarity:** Developed a function that calculates the mathematical similarity between songs based on their audio vectors.
* **Mood-Aware Filtering:** The system recommends the top $N$ most similar songs while ensuring they belong to the same mood cluster as the input track.

---

## 📦 Requirements
To run this notebook, you will need to install the following libraries:

```bash
pip install pandas numpy plotly matplotlib seaborn scikit-learn
