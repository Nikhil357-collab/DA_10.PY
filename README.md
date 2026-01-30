# DA_10.PY
TransactionAmount, CustomerAge, TransactionDuration, LoginAttempts, AccountBalance
. Data Inspection

Checked dataset shape, data types, and sample records using:
.shape()
.info()
.head()
Purpose:
To understand dataset size, feature types, and overall structure.

2. Descriptive Statistics

Generated summary statistics using .describe()
Insights:
Many numeric features are right-skewed
Presence of extreme values common in fraud-related data
Mean and median differences indicate non-normal distributions

3. Missing Value Analysis

Computed missing value percentage for each column
Insights:
Identified columns with insufficient data
Informed decisions on retention or feature engineering

4. Distribution Analysis

Plotted histograms and boxplots for numeric features
Insights:
Transaction-related features show heavy skewness
Boxplots clearly reveal extreme outliers
Visual confirmation before algorithmic outlier handling

5. Outlier Detection (IQR Method)

Used Interquartile Range (IQR) to detect outliers
Why IQR?
Robust to extreme values
Suitable for skewed financial data

6. Outlier Flag Feature

Created a binary is_outlier column
Purpose:
Helps identify anomalous transactions
Can be used as a feature in fraud models or rule-based systems

7. Outlier Handling (Capping / Winsorization)

Applied IQR-based capping instead of removing rows

Reason:
Fraud transactions often appear as outliers
Removing them may eliminate meaningful fraud cases
Capping reduces extreme influence while preserving data

8. Correlation Analysis

Generated Pearson correlation matrix for numeric features

Extracted top absolute correlations

Key Insights:

Very low multicollinearity across features

Moderate positive correlation:

CustomerAge ↔ AccountBalance (~0.32)

Most features are weakly correlated, indicating independent behavior

LoginAttempts shows NaN correlations due to zero variance or missing data
