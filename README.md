Employee Sentiment Analysis

This project analyzes employee email sentiment data to evaluate engagement, flag flight risks, and build predictive models using NLP and statistical techniques.

Setup

- Python version: 3.8+
- Required libraries:
  - pandas
  - numpy
  - matplotlib
  - seaborn
  - scikit-learn
- To install dependencies:
  pip install -r requirements.txt

Usage

1. Open the Jupyter Notebook file (e.g., main.ipynb)
2. Run all cells sequentially to:
   - Load and preprocess data
   - Label sentiment
   - Conduct EDA and generate visualizations
   - Calculate monthly sentiment scores
   - Rank employees
   - Identify flight risks
   - Train and evaluate a regression model
3. Output CSVs and visualizations will be generated during execution.



  Employee Sentiment Analysis

This project analyzes employee email sentiment data to evaluate engagement, flag flight risks, and build predictive models using NLP and statistical techniques.

  Overview

- **Language**: Python
- **Libraries**: pandas, sklearn, matplotlib, seaborn
- **Dataset**: Internal unlabeled email dataset (now labeled with sentiment)

---

  Project Tasks

 1. Sentiment Labeling
- **Goal**: Assign `Positive`, `Negative`, or `Neutral` label to each message.
- **Method**: Used TextBlob / pretrained sentiment analysis tool to analyze message body and classify sentiment.
- **Outcome**: Added a `Sentiment` column to the dataset.

 2. Exploratory Data Analysis (EDA)
- **Insights**:
  - Distribution of sentiments
  - Monthly sentiment trends over time
  - Word count distribution
  - Top message senders

 3. Monthly Sentiment Score Calculation
- **Scoring**:
  - Positive: +1
  - Negative: -1
  - Neutral: 0
- **Result**: Monthly sentiment scores computed for each employee.

 4. Employee Ranking
- **Top 3 Positive & Negative Employees**:
  - Ranked monthly by sentiment score.
  - Sorted by score (desc) then alphabetically.

 5. Flight Risk Identification
- **Rule**: Any employee with ≥4 negative emails within a 30-day rolling window.
- **Output**: List of employees at risk of leaving.

 6. Predictive Modeling
- **Model**: Linear Regression
- **Features**:
  - `message_count`
  - `avg_word_count`
- **Evaluation**:
  - R² Score: `0.434`
  - RMSE: `1.984`
- **Interpretation**: `message_count` has stronger predictive power for sentiment trends.

---

  Output Files

- `monthly_sentiment_scores.csv`: Monthly score data
- `ranked_employees.csv`: Top positive/negative employees
- `flight_risk_employees.csv`: Identified risk employees
- `model_coefficients.csv`: Regression weights
- Visualizations in `/visualizations` folder (PNG)

---

  Key Insights

- Email volume and richness (avg. word count) positively correlate with sentiment trends.
- Top positive contributors may indicate high engagement.
- Identifying flight risks early could inform HR strategy.

---

  Submission Info

- Author: Zheyu Zhao
- Contact: estherzhao1203@gmail.com
- Evaluation Contact: jbirch@glynac.ai
