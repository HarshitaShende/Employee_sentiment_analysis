# Employee Sentiment Analysis

## Project Overview
This project analyzes employee email communications to assess sentiment and engagement using Natural Language Processing (NLP) and statistical analysis techniques.  
The dataset provided was unlabeled, and sentiment was automatically inferred using the VADER sentiment analyzer.

The analysis includes sentiment labeling, exploratory data analysis, employee scoring, ranking, flight risk identification, and predictive modeling.

---

## Dataset
- File: `test.csv`
- Data Type: Employee email messages
- Fields Used:
  - `from`: Employee identifier
  - `Subject`: Email subject
  - `body`: Email content
  - `date`: Timestamp of message

---

## Sentiment Labeling Approach
- Tool Used: **VADER Sentiment Analyzer**
- Labels:
  - Positive
  - Neutral
  - Negative
- Classification based on compound sentiment score:
  - ≥ 0.05 → Positive  
  - ≤ -0.05 → Negative  
  - Otherwise → Neutral  

### Sentiment Distribution
- Positive: **1545**
- Neutral: **382**
- Negative: **264**

---

## Employee Monthly Sentiment Scoring
- Positive message → +1  
- Negative message → -1  
- Neutral message → 0  
- Scores are aggregated per employee per month and reset monthly.

---

## Employee Ranking
For each month:
- **Top 3 Positive Employees** identified based on highest sentiment scores.
- **Top 3 Negative Employees** identified based on lowest sentiment scores.
- Ties are resolved alphabetically by employee identifier.

---

## Flight Risk Identification
An employee is flagged as a **flight risk** if:
- They have sent **4 or more negative messages within any rolling 30-day window**.
- Month boundaries are ignored as per requirements.

This logic helps identify employees with sustained dissatisfaction patterns.

---

## Predictive Modeling
- Model Used: **Linear Regression**
- Target Variable: Monthly sentiment score
- Features:
  - Message count per month
  - Average message length
  - Total message length
  - Negative message count

### Model Insights
- Negative message count has the strongest negative influence on sentiment score.
- Higher engagement (message frequency) generally correlates with better sentiment.
- Message length reflects emotional intensity.

---

## Key Insights & Recommendations
- Majority of communications show positive sentiment, indicating healthy engagement.
- A small subset of employees show repeated negative sentiment patterns and should be monitored.
- Regular sentiment tracking can help proactively identify engagement issues.

---

## Repository Structure
Employee-Sentiment-Analysis/
├── data/
│ └── test.csv
├── notebooks/
│ └── employee_sentiment_analysis.ipynb
├── visualizations/
├── README.md

## Author
**Harshita S. Shende**
