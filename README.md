# MSCS_634_Project

This project focuses on analyzing and predicting employee salaries using a real-world dataset retrieved from Kaggle. The dataset contains features such as age, gender, education level, job title, years of experience, and current salary. I chose this dataset because it closely aligns with real-world HR analytics challenges, including understanding compensation patterns, identifying demographic disparities, and predicting salary outcomes. The project explores multiple aspects of data mining: regression modeling for salary prediction, classification of salary categories, clustering to uncover natural groupings, and association rule mining to detect hidden patterns.

## Dataset

The dataset includes 375 records with the following key features:
	•	Age: Numeric, employee age in years
	•	Gender: Categorical, male or female
	•	Education Level: Ordinal categorical (High School → Bachelor → Master → PhD)
	•	Job Title: Nominal categorical, varies by employee role
	•	Years of Experience: Numeric
	•	Salary: Numeric, annual salary in USD

## Project Steps

### 1. Data Preparation

I began by removing a small number of missing values (2 per column) to ensure dataset integrity. Exploratory Data Analysis (EDA) included histograms, scatter plots, boxplots, and a correlation heatmap to understand distributions and relationships among features. Categorical features were encoded using LabelEncoder (Gender), OrdinalEncoder (Education Level), and OneHotEncoder (Job Title). Numerical features were standardized, and basic feature engineering was performed, including creating bins for years of experience and salary categories. An 80/20 train-test split was applied to prevent data leakage.

### 2. Modeling
	•	Regression Models: Linear Regression and Lasso Regression were implemented to predict salaries as a continuous variable. Feature engineering and interaction terms enhanced predictive power.
	•	Classification Models: Decision Tree and tuned SVM models were used to classify salaries into categories.
	•	Clustering: K-Means clustering identified natural groupings in the dataset. The elbow method suggested four clusters, separating entry-level employees from mid-career professionals.
	•	Association Rule Mining: FP-Growth extracted patterns linking salary levels with gender, education, and experience, highlighting strong co-occurrences and potential pathways for career advancement.


## Findings

Regression

| Model | R² | MSE | RMSE |
| ----- | ----- | ----- | ----- | 
| Linear Regression | 0.8247 | 420,384,287.74 | 20,503.28 |
| Lasso Regression | 0.8271 | 414,594,524.94 | 20,361.59 |

Classification


| Model | Accuracy | F1-Score| 
| ----- | ----- | ----- |
| Decision Tree | 0.40 | 0.34 |
| SVM | 0.37 | 0.33 |

Clustering

| Cluster | Age | Years of Experience | Salary |
|-----|-----|-----|-----|
| 0 | 43.00 | 14.00 | 120,000 |
| 1 | 41.26 | 13.59 | 126,402 |
| 2 | 42.00 | 14.00 | 115,000 |
| 3 | 29.81 | 2.95 |49,483 |

Association Rule Mining

FP-Growth revealed strong patterns such as: Employees who are female and have very high salaries often hold a PhD (Lift ≈ 4.04, Confidence ≈ 55%) and Employees with over 20 years of experience are likely to earn very high salaries (Lift ≈ 3.92, Confidence ≈ 89%).


## Insights

From this project, several important insights emerged:
	1.	Experience and education are the strongest predictors of salary, aligning with labor-market expectations.
	2.	Regression models outperform classification models, confirming that salary behaves more like a continuous variable than discrete categories.
	3.	Clustering identifies a distinct early-career group, useful for designing targeted HR policies.
	4.	Association rules highlight strong co-occurrences, particularly around PhD holders and high salaries, revealing potential career advancement pathways.


## Ethical Considerations

Salary data involves sensitive information, requiring careful attention to bias, fairness, and privacy:
	•	Gender and demographic bias: Historical inequities may be reflected in the data
	•	Algorithmic transparency: Clear communication is essential for pay-related decisions
	•	Data privacy: Strong protections are needed for sensitive employee information 

Recommendations:
	1.	Conduct fairness audits to ensure model predictions do not reinforce disparities
	2.	Adopt transparency measures like model cards to document model behavior 
	3.	Strengthen data governance by anonymizing identifiers and restricting access to sensitive data.



