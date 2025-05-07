# 🎮 IMDb Movies Data Analysis

This project performs an exploratory data analysis (EDA) on a dataset of movies sourced from IMDb. The goal is to uncover trends in movie production, popularity, budgets, languages, and more using Python.

---

## 📁 Dataset Overview

**File**: `imdb_data.csv`
**Size**: \~23 columns with over 4,800+ movie entries.

### Key Columns:

* `title`, `original_title`
* `budget`, `revenue`, `runtime`
* `genres`, `keywords`, `cast`, `crew`
* `original_language`, `release_date`, `popularity`

---

## 🧰 Technologies Used

* Python
* Jupyter Notebook
* pandas, matplotlib, seaborn, numpy
* JSON parsing for nested fields

---

## 📊 Key Visualizations

### 1. Movie Releases Over the Years

```python
imdb_df['release_year'] = pd.to_datetime(imdb_df['release_date'], errors='coerce').dt.year
imdb_df['release_year'].value_counts().sort_index().plot(kind='bar', figsize=(14, 5))
plt.title('Number of Movies Released Each Year')
plt.xlabel('Year')
plt.ylabel('Number of Movies')
plt.show()
```

### 2. Top 10 Highest Revenue Movies

```python
top_revenue = imdb_df.sort_values(by='revenue', ascending=False).head(10)
sns.barplot(data=top_revenue, y='title', x='revenue')
plt.title('Top 10 Highest Grossing Movies')
plt.xlabel('Revenue')
plt.ylabel('Movie Title')
plt.show()
```

### 3. Budget vs Revenue Scatter Plot

```python
sns.scatterplot(data=imdb_df, x='budget', y='revenue')
plt.title('Budget vs Revenue')
plt.xlabel('Budget')
plt.ylabel('Revenue')
plt.show()
```

### 4. Most Common Languages

```python
imdb_df['original_language'].value_counts().head(10).plot(kind='barh')
plt.title('Most Common Languages in Movies')
plt.xlabel('Number of Movies')
plt.ylabel('Language')
plt.show()
```

---

## 🔍 Insights

* English dominates the original language of most movies.
* Many movies earn far less than their budget, indicating risk.
* Some years (e.g. 2015, 2016) had a spike in movie production.
* A handful of blockbuster movies account for a major chunk of total revenue.

---

## ▶️ How to Run

1. Clone this repository:

   ```bash
   git clone https://github.com/your-username/imdb-movie-analysis.git
   cd imdb-movie-analysis
   ```
2. Open `IMDB_Movies_data_analysis.ipynb` in Jupyter Notebook or VS Code.
3. Run cells to execute the analysis.

---

## 🙌 Contributions

Feel free to fork the repo and suggest changes, add visualizations, or apply machine learning for deeper analysis!

---

## 📢 Contact

Have questions or feedback? Reach me at \[[your.email@example.com](mailto:your.email@example.com)].
