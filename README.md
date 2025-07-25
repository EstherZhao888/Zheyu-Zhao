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
-                                                 body Sentiment
 EnronOptions Announcement\n\n\nWe have updated...  Positive
 Marc,\n\nUnfortunately, today is not going to ...   Neutral
 When: Wednesday, June 06, 2001 10:00 AM-11:00 ...   Neutral
 We were thinking papasitos (we can meet somewh...  Negative
 Since you never gave me the $20 for the last t...   Neutral

 Sentiment
Neutral     1056
Positive     971
Negative     164
Name: count, dtype: int64

 2. Exploratory Data Analysis (EDA)
- **Insights**:
  - Distribution of sentiments
  - Monthly sentiment trends over time
  - Word count distribution
  - Top message senders
    <img width="611" height="384" alt="Figure EDA 3 0_副本" src="https://github.com/user-attachments/assets/630c1775-e036-4b72-b968-0b000f0de465" />

 3. Monthly Sentiment Score Calculation
- **Scoring**:
  - Positive: +1
  - Negative: -1
  - Neutral: 0
  -                       Employee    Month  Monthly_Sentiment_Score
0  bobette.riner@ipgdirect.com  2010-01                        2
1  bobette.riner@ipgdirect.com  2010-02                        7
2  bobette.riner@ipgdirect.com  2010-03                        4
3  bobette.riner@ipgdirect.com  2010-04                        2
4  bobette.riner@ipgdirect.com  2010-05                        1
- **Result**: Monthly sentiment scores computed for each employee.

 4. Employee Ranking
- **Top 3 Positive & Negative Employees**:
  - Ranked monthly by sentiment score.
  - Sorted by score (desc) then alphabetically.
                        Employee    Month  Monthly_Sentiment_Score  \
192      rhonda.denton@enron.com  2010-01                        0   
96       johnny.palmer@enron.com  2010-01                        1   
0    bobette.riner@ipgdirect.com  2010-01                        2   
120      kayne.coulter@enron.com  2010-01                        5   
168     patti.thompson@enron.com  2010-01                        5   
..                           ...      ...                      ...   
95         john.arnold@enron.com  2011-12                        2   
119      johnny.palmer@enron.com  2011-12                        2   
143      kayne.coulter@enron.com  2011-12                        5   
191     patti.thompson@enron.com  2011-12                        5   
71           eric.bass@enron.com  2011-12                        4   

 5. Flight Risk Identification
- **Rule**: Any employee with ≥4 negative emails within a 30-day rolling window.
- **Output**: List of employees at risk of leaving.
-                       Employee
0  bobette.riner@ipgdirect.com
1        john.arnold@enron.com
2         sally.beck@enron.com
3      lydia.delgado@enron.com
4      johnny.palmer@enron.com
5      rhonda.denton@enron.com
6     patti.thompson@enron.com

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
