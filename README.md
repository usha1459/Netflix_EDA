# Netflix Exploratory Data Analysis (EDA)

## 📌 Project Overview
This project performs **Exploratory Data Analysis (EDA)** on the **Netflix Titles Dataset (2021)** to uncover insights about Movies and TV Shows available on Netflix. The analysis includes:
- Distribution of Movies vs. TV Shows
- Correlation analysis
- Most watched shows and ratings distribution
- Content release trends over the years
- Popular genres and directors
- Country-wise and rating-based insights

## 📂 Dataset
**Dataset Name:** `netflix_titles_2021.csv`

**Source:** [Kaggle Netflix Dataset](https://www.kaggle.com/shivamb/netflix-shows) 

**Columns:**
- `show_id`: Unique ID for each title
- `type`: Movie or TV Show
- `title`: Name of the show
- `director`: Director of the title
- `cast`: Cast members
- `country`: Country where the title was produced
- `date_added`: Date when the title was added to Netflix
- `release_year`: Release year of the title
- `rating`: Content rating (PG, TV-MA, etc.)
- `duration`: Duration of movies (in minutes) or number of seasons for TV shows
- `listed_in`: Genre categories
- `description`: Short description of the title

## 📊 Exploratory Data Analysis (EDA)
### 1️⃣ **Understanding the Dataset**
- Displaying the first few rows using `df.head()`
- Checking data types and missing values using `df.info()`
- Getting summary statistics with `df.describe(include='object')`

### 2️⃣ **Distribution of Movies vs. TV Shows**
- `sns.countplot(data=df, x="type", palette=["royalblue", "darkorange"])`

### 3️⃣ **Correlation Analysis**
- Calculating correlation between numerical features using `.corr()`

### 4️⃣ **Most Watched Shows on Netflix**
- `df['title'].value_counts().head(1)`

### 5️⃣ **Distribution of Ratings**
- `sns.countplot(data=df, y="rating", order=df['rating'].value_counts().index)`

### 6️⃣ **Movies vs. TV Shows: Rating Analysis**
- Grouping ratings by type and visualizing with `sns.barplot()`

### 7️⃣ **Best Month for Releasing Content**
- Extracting month from `date_added`
- Finding the most frequent month for content releases

### 8️⃣ **Most Popular Genres**
- `df['listed_in'].value_counts().head(1)`

### 9️⃣ **Movies Released Over the Years**
- `sns.histplot(df[df["type"] == "Movie"]["release_year"], bins=30, kde=True, color='teal')`

### 🔟 **Movies Made on a Yearly Basis**
- `sns.barplot(x=movies_per_year.index, y=movies_per_year.values, palette="coolwarm")`

### 1️⃣1️⃣ **Finding Specific Titles**
- Searching for "House of Cards" using `df[df['title'] == "House of Cards"][["show_id", "director"]]`
- Filtering TV Shows released in India

### 1️⃣2️⃣ **Actor-Based Insights**
- Finding all titles featuring "Tom Cruise"
- Counting how many movies got the "TV-14" rating in Canada

## 📈 Visualizations Used
- **Histograms & KDE Plots** (For distribution analysis)
- **Count Plots** (For categorical data like ratings & genres)
- **Bar Charts** (For yearly trends & comparisons)
- **Pie Charts** (For distribution breakdowns)

## 💻 Technologies Used
- **Python**
- **Pandas**
- **NumPy**
- **Matplotlib & Seaborn**
- **Jupyter Notebook / Google Colab**

## 🚀 How to Run the Project
1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/netflix-eda.git
   ```
2. Install required libraries:
   ```bash
   pip install pandas numpy matplotlib seaborn
   ```
3. Run the Jupyter Notebook or Python script:
   ```bash
   jupyter notebook
   ```
   Open the notebook and execute the cells step by step.

## 📌 Future Improvements
- Sentiment analysis on show descriptions
- Predictive modeling for content trends
- More interactive visualizations using Plotly

---

Feel free to contribute by raising issues or submitting pull requests! 😊

