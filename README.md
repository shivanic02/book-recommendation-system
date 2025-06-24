# 📚 Book Recommendation System

This project builds a **collaborative filtering-based recommender system** that suggests books to users based on their personal preferences and previous ratings. The model leverages **sparse matrix operations** and **cosine similarity** to efficiently generate recommendations for over 100,000 users.

---

## 📘 Project Overview

This project was completed as part of **IFT 511: Analyzing Big Data** at **Arizona State University**.

---

## 📊 Dataset Description

The Book Crossing dataset can be downloaded through Kaggle:

https://www.kaggle.com/datasets/somnambwl/bookcrossing-dataset?resource=download

It consists of three files:

1. Books.csv
  Contains information about different books such as book title, description, author, ISBN, etc.

2. Users.csv
  Contains user IDs and ages.

3. Ratings.csv
  Contains users' ratings of different books.

The dataset contains:

Over 270,000 books
Over 270,000 books 
Over 1 Million ratings given by users to books
The rating scale goes from 0 to 10.

---

## 🔍 Features

- Loads and processes the Book-Crossing dataset
- Converts user-book ratings into a **sparse matrix** using `scipy`  
- Computes **cosine similarity** between users for collaborative filtering  
- Recommends top 5 books for each user based on estimated preference scores  
- Saves results to a CSV file with recommendation scores  

---

## 🛠 Technologies Used

- Python  
- Pandas, NumPy  
- Scikit-learn (`load_svmlight_file`)  
- SciPy Sparse Matrices (`csr_matrix`)  
- Cosine Similarity for large-scale user-user comparisons  

---

## 📂 File Structure

- `Ratings.csv` – Raw user-book ratings  
- `Sparse Matrix-1.ipynb` – Code for preparing the sparse matrix  
- `Project Step-2.ipynb` – Recommendation engine logic and similarity scoring  
- `user_book_ratings.libsvm` – LIBSVM format file used for efficient loading  
- `recommendations_105283_users_new.csv` – Final output containing top book recommendations  

---

## 🚀 How It Works

1. **Preprocessing**  
   - Cleans and encodes `User-ID` and `ISBN` as numerical indices  
   - Creates a sparse matrix where rows = users and columns = books

2. **Similarity Calculation**  
   - Uses cosine similarity to find the top 10 similar users for each user

3. **Recommendation Generation**  
   - Aggregates highly rated books from similar users  
   - Filters out already-read books  
   - Outputs top 5 new books per user with estimated preference scores

---

## 📊 Output

Each row in the output CSV contains:
- `User_ID`: Internal index of the user
- `Book_IDs`: Top recommended books for that user (by internal index)
- `Recommendation_Scores`: Relevance scores for each recommendation

---

## 💡 Future Improvements

- Add content-based filtering using book metadata
- Integrate with a frontend UI
- Use implicit feedback and matrix factorization models (e.g., SVD or ALS)

---


> **Note:** This was an academic project for educational purposes under the guidance of the IFT 511 course at Arizona State University.
