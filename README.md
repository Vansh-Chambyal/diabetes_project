# diabetes_project

"This project is an end-to-end machine learning pipeline to predict the risk of hospital readmission for diabetes patients. The goal is to classify a patient into one of three categories: being readmitted in less than 30 days, more than 30 days, or not at all. This is a critical problem for hospitals, as reducing early readmissions improves patient care and lowers costs.

# My process involved two main stages:

# Preprocessing & Feature Engineering: 
The raw data was very messy, with 50 columns and thousands of unique diagnosis codes.

# First
I cleaned the data by dropping columns with high missing values (like weight) and irrelevant IDs.

My most important step was feature engineering. The diag_1, diag_2, and diag_3 columns were raw ICD-9 codes, which are not suitable for a model. I wrote a function to map these thousands of codes into 9 broad clinical categories (like 'Circulatory', 'Respiratory', 'Diabetes'). This made the feature far more useful.

I then built a ColumnTransformer pipeline to automatically StandardScale all numerical features and OneHotEncode all categorical features.

# Finally
I saved this entire preprocessing pipeline as a preprocessor.joblib file.

# Model Tuning & Selection:

I loaded the clean data and trained a LogisticRegression model as a simple baseline.

I then trained a RandomForestClassifier, which performed much better, proving the relationships in the data were complex.

To get the best performance, I used GridSearchCV to automatically tune the Random Forest's hyperparameters.

I saved this final, optimized model as best_random_forest_model.pkl.

The final result is a complete, saved pipeline. I have a predict.py script that can load these saved files to take in new, raw patient data and instantly produce a reliable prediction of their readmission risk."
