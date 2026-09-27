
# 📊 Social Media Engagement Analytics Using Python

This project performs an end-to-end social media engagement analysis on a 5,000-record dataset using Python. It covers data cleaning, feature engineering, exploratory data analysis (EDA), statistical analysis, visualization, and business-oriented insight generation.

The objective is to transform raw social media data into meaningful insights that explain what content performs well, which audiences engage more, and how behavioral factors relate to engagement.

---

## 📌 Project Overview

This project analyzes a 5,000-record social media engagement dataset using Python. The analysis focuses on understanding:

- Content performance  
- User behavior  
- Engagement patterns  
- Posting behavior  
- Sentiment-based performance  

The project follows a complete data analysis workflow:

1. Data import and setup  
2. Data cleaning and preprocessing  
3. Exploratory Data Analysis (EDA)  
4. Data wrangling and feature engineering  
5. Statistical analysis  
6. Data visualization  
7. Business-oriented insight generation  

---

## 🎯 Problem Statement

Social media platforms generate large volumes of engagement data such as likes, comments, shares, impressions, watch time, and follower counts. Analyzing these metrics helps identify user behavior, content trends, and engagement patterns.

This project uses Python to clean, transform, explore, visualize, and analyze social media engagement data and generate actionable insights.

---

## 📂 Dataset

**Dataset:** `social_media_engagement_5000.csv`  

**Dataset Size:**
- Rows: 5,000  
- Original columns: 19  
- Additional derived features: `engagement_score`, `hashtag_count`, log-transformed metrics, `age_group`, `posting_hour`  

**Main Columns:**

| Column            | Description                                      |
|-------------------|--------------------------------------------------|
| `user_id`         | Unique user identifier                           |
| `age`             | User age                                         |
| `gender`          | User gender                                      |
| `country`         | User country                                     |
| `post_id`         | Unique post identifier                           |
| `post_type`       | Type of post (image, reel, text, video)          |
| `post_category`   | Content category                                 |
| `likes`           | Number of likes                                  |
| `comments`        | Number of comments                               |
| `shares`          | Number of shares                                 |
| `watch_time_sec`  | Watch time in seconds                            |
| `impression_count`| Number of impressions                            |
| `posted_at`       | Post date/time                                   |
| `follower_count`  | Number of followers                              |
| `is_verified`     | Verified account status                          |
| `device_type`     | Device used                                      |
| `sentiment`       | Sentiment classification                         |
| `hashtags`        | Hashtags associated with the post                |
| `engagement_rate` | Engagement rate                                  |

---

## 🛠️ Technologies and Tools Used

- Python  
- Pandas  
- NumPy  
- Matplotlib  
- Seaborn  
- Jupyter Notebook  

---

## 🔄 Project Workflow

### 1. Data Import & Setup

- Imported the CSV dataset using `pandas.read_csv()`  
- Inspected the dataset using:
  - `head()`, `tail()`, `shape`, `columns`, `info()`, `dtypes`  
- Converted the `posted_at` column to datetime format  
- Converted appropriate numerical and categorical columns to suitable data types  

### 2. Data Cleaning

**Missing Value Handling**
- Identified missing values using `isnull()` and `isna()`  
- Handled missing categorical values using the mode:
  - 150 missing `gender` values  
  - 150 missing `sentiment` values  

**Duplicate Handling**
- Identified and removed duplicate records where applicable  

**Data Formatting**
- Corrected numerical data types  
- Converted categorical columns to Pandas `category` dtype  
- Standardized categorical values  
- Checked for unrealistic values in engagement metrics  

**Feature Cleaning**
- Extracted hashtag counts  
- Cleaned sentiment labels using string operations (`str.strip()`, `str.lower()`)  

---

## 🔍 Exploratory Data Analysis

The following Pandas techniques were used:

**Dataset Structure**
- `df.head()`, `df.tail()`, `df.shape`, `df.columns`, `df.info()`, `df.dtypes`  

**Summary Statistics**
- `df.describe()` to analyze mean, standard deviation, min, max, and quartiles  

**Categorical Analysis**
- `value_counts()`, `unique()`, `nunique()` to examine distributions of:
  - Gender, Country, Post type, Post category, Device type, Sentiment, Verification status  

**Correlation Analysis**
- Created a correlation matrix for numerical variables using:
  ```python
  df.select_dtypes(include=['int64', 'float64']).corr()
  ```

**GroupBy Analysis**
- Used `groupby()` and `agg()` to compare:
  - Likes by post type  
  - Impressions by country  
  - Engagement score by post type, country, and sentiment  
  - Engagement rate by post type, category, and country  

---

## 📊 Statistical Analysis

Descriptive statistics were calculated for:
- Likes, Comments, Shares, Watch time, Engagement rate, Follower count  

**Selected Results:**

| Metric             | Mean        | Median      |
|--------------------|-------------|-------------|
| Likes              | 10,107.04   | 10,105.50   |
| Comments           | 1,502.20    | 1,497.00    |
| Shares             | 1,002.63    | 1,012.00    |
| Watch Time (sec)   | 4,014.50    | 4,034.50    |
| Engagement Rate    | 0.964       | 0.254       |
| Follower Count     | 393,698.22  | 388,982.00  |

The engagement rate has a substantially higher maximum than its median, indicating that a smaller number of observations have particularly high engagement rates.

---

## 📈 Data Visualization

### Matplotlib Visualizations

- Scatter Plot — Likes vs Impressions  
- Line Chart — Daily Engagement Trend  
- Bar Chart — Posts by Category  
- Pie Chart — Gender Distribution  
- Histogram — Age Distribution  
- Box Plot — Engagement Rate Distribution  

### Seaborn Visualizations

- Count Plot — Post Type  
- Bar Plot — Average Likes by Category  
- Violin Plot — Follower Count vs Sentiment  
- Pair Plot — Numeric Features  
- Heatmap — Correlation Matrix  

---

## 🔎 Final Insights

### 1. Content Performance

**Highest-Engagement Post Type**

| Post Type | Average Engagement Rate |
|-----------|--------------------------|
| Video     | 1.1224                   |
| Text      | 1.0645                   |
| Image     | 0.8956                   |
| Reel      | 0.7830                   |

> **Insight:** Video posts recorded the highest average engagement rate at 1.1224.

**Best-Performing Content Category**

| Category  | Average Engagement Rate |
|-----------|--------------------------|
| Food      | 1.3586                   |
| Tech      | 1.1605                   |
| Lifestyle | 1.0910                   |
| Music     | 0.8888                   |
| Fitness   | 0.8656                   |
| Education | 0.8442                   |
| Fashion   | 0.8071                   |
| Travel    | 0.7022                   |

> **Insight:** The Food category recorded the highest average engagement rate at 1.3586.

**Countries with Highest Average Engagement Rate**

| Country   | Average Engagement Rate |
|-----------|--------------------------|
| Brazil    | 1.5407                   |
| Australia | 1.3243                   |
| France    | 1.1464                   |
| UAE       | 1.1124                   |
| Canada    | 0.9167                   |
| UK        | 0.8510                   |
| Japan     | 0.7696                   |
| Germany   | 0.7590                   |
| India     | 0.6550                   |
| USA       | 0.5766                   |

> **Insight:** Brazil recorded the highest average engagement rate in the analyzed dataset.

---

### 2. User Trends

**How Age Affects Engagement**

| Age Group | Average Engagement Rate |
|-----------|--------------------------|
| <18       | 0.8670                   |
| 18–25     | 1.0595                   |
| 26–35     | 0.8653                   |
| 36–45     | 0.8586                   |
| 46–55     | 1.4141                   |
| 56–65     | 0.7092                   |

> **Insight:** The 46–55 age group recorded the highest average engagement rate at 1.4141.

**Verified vs Non-Verified Accounts**

| Account Status | Average Engagement Rate |
|----------------|--------------------------|
| Verified       | 1.0543                   |
| Non-Verified   | 0.9547                   |

> **Insight:** Verified accounts had higher average engagement than non-verified accounts.

---

### 3. Behavioral Insights

**Best Time of Day for Impressions**

- Hour: 0  
- Average impressions: 50,013.73  

> ⚠️ **Data Limitation:** The `posted_at` values appear to contain dates without reliable time-of-day information, often defaulting to midnight (00:00). Therefore, the result of hour 0 should not be interpreted as evidence that midnight is the best posting time.

**Device Type Impact on Watch Time**

| Device Type | Average Watch Time (sec) |
|-------------|---------------------------|
| Mobile      | 4,087.83                  |
| Tablet      | 3,979.74                  |
| Desktop     | 3,974.79                  |

> **Insight:** Mobile users recorded the highest average watch time.

---

### 4. Sentiment Analysis

**Which Sentiment Performs Best?**

| Sentiment | Average Engagement Rate |
|-----------|--------------------------|
| Negative  | 1.0385                   |
| Neutral   | 0.9912                   |
| Positive  | 0.9548                   |

> **Insight:** Negative-sentiment posts recorded the highest average engagement rate.

**Behavior of Negative and Neutral Posts**

| Sentiment | Avg Likes | Avg Comments | Avg Shares | Avg Impressions | Engagement Rate |
|-----------|-----------|--------------|------------|------------------|------------------|
| Negative  | 10,211.41 | 1,516.58     | 1,007.19   | 50,191.96        | 1.0385           |
| Neutral   | 9,917.79  | 1,529.27     | 996.15     | 49,515.97        | 0.9912           |

> **Insight:** Negative posts generated higher average likes, shares, impressions, and engagement rate than neutral posts.

---

## 💡 Key Takeaways

- Video posts had the highest average engagement rate among post types.  
- Food was the highest-performing content category by average engagement rate.  
- Brazil recorded the highest average engagement rate among the analyzed countries.  
- Engagement varied considerably across age groups, with the 46–55 group showing the highest average engagement.  
- Verified accounts showed higher average engagement than non-verified accounts.  
- Mobile users had the highest average watch time.  
- Negative-sentiment posts recorded the highest average engagement rate.  
- Negative posts generated higher average impressions and overall interaction metrics than neutral posts.  
- Correlation analysis showed generally weak relationships among many numerical variables.  
- The posting-hour result requires caution due to incomplete timestamp information.  

---

## 📁 Project Structure

```text
Social-Media-Engagement-Analytics/
│
├── 📄 social_media_engagement_5000.csv
├── 📓 Social_Media_Engagement_Analytics.ipynb
├── 📄 README.md
│
└── 📁 images/
    ├── likes_vs_impressions.png
    ├── daily_engagement_trend.png
    ├── posts_by_category.png
    ├── gender_distribution.png
    ├── age_distribution.png
    ├── engagement_rate_distribution.png
    ├── post_type_count.png
    ├── average_likes_by_category.png
    ├── followers_vs_sentiment.png
    ├── pairplot.png
    └── correlation_heatmap.png
```

---

## 🚀 Skills Demonstrated

- Python for Data Analysis  
- Pandas Data Manipulation  
- NumPy Operations  
- Data Cleaning  
  - Missing Value Handling  
  - Duplicate Handling  
  - Data Type Conversion  
  - Categorical Data Handling  
  - Datetime Processing  
- Feature Engineering  
- GroupBy and Aggregation  
- Descriptive Statistics  
- Correlation Analysis  
- Exploratory Data Analysis  
- Matplotlib Visualization  
- Seaborn Visualization  
- Business Insight Generation  
- Data Storytelling  

---
## 📝 Conclusion

This project demonstrates how Python can be used to perform an end-to-end social media engagement analysis. Through data cleaning, feature engineering, exploratory analysis, statistical techniques, visualization, and group-based comparisons, the project identified meaningful differences in engagement across post types, content categories, countries, age groups, verification status, device types, and sentiment.

The analysis shows that engagement behavior is influenced by multiple dimensions rather than a single factor. In this dataset, video content, food-related content, verified accounts, mobile usage, and negative-sentiment posts were associated with higher measured engagement rates.

The project also highlights an important data-quality principle: insights are only as reliable as the underlying data. In particular, the posting-time analysis demonstrates why complete timestamp information is necessary before making conclusions about the best time to publish content.

Overall, the project provides practical experience in using Pandas, NumPy, Matplotlib, and Seaborn to convert raw social media data into structured analysis and business-oriented insights.

---

## 👩‍💻 Author

**Idaya Gracy Jude**  
Aspiring Data Analyst | Python | SQL | Power BI | Excel  

---


## 📬 Contact

Feel free to reach out for collaborations or feedback on this project.
