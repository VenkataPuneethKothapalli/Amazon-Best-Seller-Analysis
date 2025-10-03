# 📚 Amazon-Best-Seller-Analysis

This project performs a preliminary analysis of a dataset containing information on bestselling books, likely sourced from a major retailer like Amazon. The analysis focuses on identifying the most frequent top-selling authors and comparing user ratings between Fiction and Non Fiction genres.

---

## 📁 Project Structure

| File Name | Description |
| :--- | :--- |
| `bestsellers.csv` | The **raw dataset** containing book titles, authors, user ratings, reviews, prices, publication years, and genre. |
| `main.py` | The Python script (using **pandas**) responsible for data cleaning, analysis, and generating the summary reports. |
| `avg_rating_by_genre.csv` | **Generated output**: Summarizes the mean user rating for Fiction and Non Fiction genres. |
| `top_authors.csv` | **Generated output**: Lists the top 10 authors based on their number of bestseller appearances in the dataset. |

---

## ⚙️ Analysis Performed (`main.py`)

The `main.py` script executes the following key steps:

1.  **Data Loading & Cleaning**:
    * Loads `bestsellers.csv`.
    * Removes **duplicate entries** (as a book can be a bestseller in multiple years).
    * Renames columns for clarity: "Name" → **"Title"**, "User Rating" → **"Rating"**, "Year" → **"Publication Year"**.
    * Converts the "Price" column to a float data type.

2.  **Author Popularity Analysis**:
    * Calculates the frequency of each author's appearance on the bestseller list (`Author.value_counts()`).
    * Exports the top 10 authors to `top_authors.csv`.

3.  **Genre Rating Comparison**:
    * Calculates the **average user rating** by grouping the data by "Genre" (`groupby("Genre")`).
    * Exports the results to `avg_rating_by_genre.csv`.

---

## 📊 Key Findings

### Top Bestselling Authors

The top author in the dataset, based on the number of bestseller appearances, is **Jeff Kinney** (author of the *Diary of a Wimpy Kid* series).

| Author | Bestseller Count |
| :--- | :--- |
| Jeff Kinney | 12 |
| Gary Chapman | 11 |
| Rick Riordan | 11 |
| Suzanne Collins | 11 |

### Average User Rating by Genre

| Genre | Average User Rating (Rating) |
| :--- | :--- |
| Fiction | 4.6483 |
| Non Fiction | 4.5952 |

**Conclusion**: Bestselling **Fiction** books have a slightly higher average user rating ($\approx 4.65$) than **Non Fiction** books ($\approx 4.60$).
