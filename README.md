# 🎬 Movie Recommendation System

This is a **Movie Recommendation System** built with **Python and Streamlit**.  
The goal of this project is to recommend movies similar to the one selected by the user, based on different features like genres, cast, crew, keywords, and overview.  

It is a **Content-Based Recommendation System** that uses **Natural Language Processing (NLP)** and **Cosine Similarity** to measure how closely related two movies are.

---

## 🚀 Project Overview
The system works in two main parts:

1. **Data Preprocessing & Model Building (`Main.py`)**
   - Used the **TMDB 5000 Movies Dataset** (movies + credits) from Kaggle.
   - Merged and cleaned the dataset, keeping only the necessary columns:
     - `genres`, `keywords`, `title`, `cast`, `crew`, `overview`
   - Extracted features like:
     - Genres of the movie
     - Keywords describing the movie (superhero, friendship, space, etc.)
     - Cast (top 3 actors)
     - Crew (director name)
     - Overview (short description of the movie)
   - Combined all these features into a single **tags column**.
   - Applied **text preprocessing**:
     - Tokenization
     - Removing spaces
     - Converting text to lowercase
     - Stemming using **NLTK PorterStemmer**
   - Converted text into numerical vectors using **CountVectorizer**.
   - Calculated **Cosine Similarity** between all movies to measure similarity.

2. **Recommendation Web App (`app.py`)**
   - Built with **Streamlit**.
   - User selects a movie from the dropdown.
   - System recommends **Top 5 similar movies** using precomputed similarity scores.
   - Simple and interactive UI for quick recommendations.

---

## 🛠️ Technologies Used
- **Python**
- **Pandas & NumPy** (data processing)
- **NLTK (PorterStemmer)** (text preprocessing)
- **Scikit-learn** (CountVectorizer, Cosine Similarity)
- **Streamlit** (web app framework)
- **Pickle** (for saving and loading models)

---

## 📂 Project Files
- **Main.py** → Data preprocessing, feature extraction, similarity calculation, and saving models.
- **app.py** → Streamlit app for user interaction and movie recommendations.
- **movies.pickel** → Preprocessed movie metadata.
- **similarity.pkl** → Precomputed similarity matrix.

## Install dependencies:
pip install -r requirements.txt
Run the Streamlit app:
streamlit run app.py
Select a movie from the dropdown and get Top 5 recommended movies 🎥.

## 📊 Dataset
TMDB 5000 Movies Dataset (Kaggle)
Contains movie details including cast, crew, genres, and keywords.

