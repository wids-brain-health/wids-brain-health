# WIDS Team 13
### Tiffney Aina, Wei Ding, Erynn Gutierrez, Ivi Fung

Tiffney: https://github.com/tiffaina

Wei: https://github.com/Wei0015

Erynn: https://github.com/Erynn-Gutierrez

Ivi: https://github.com/MostEsteemedFungus

## Project Highlights
This project uses fMRI data and socio-demographic information to predict ADHD diagnoses and sex of children and adolescents. The model applies a MultiOutputClassifier with a RandomForestClassifier for hyperparameter optimization, balanced training via SMOTE, and feature selection based on model importance. The final model achieved a prediction accuracy of 72.4%. Key features include ADHD diagnosis (0/1) and participant sex (0/1), utilizing both functional connectome matrices and socio-demographic data.

## Setup & Execution  
To reproduce the project:  

git clone https://github.com/wids-brain-health
Run all cells in Colab Notebook

## Project Overview
The WiDS Datathon 2025 Global Challenge on Kaggle is a predictive modeling challenge focused on analyzing electronic health records (EHRs) to forecast patient risk levels in hospitals. While the Break Through Tech AI Program (BTTAI) isn’t directly linked to this specific competition, initiatives like BTTAI  encourage participation in such events to provide students with hands-on AI/data science experience. Competitions like this align with Break Through Tech’s mission to bridge classroom learning with real-world applications, fostering skills in machine learning and healthcare analytics.

The challenge aims to build a model that accurately predicts patient risk using EHR data, enabling proactive care and resource optimization. This work has critical real-world significance: it could improve patient outcomes by identifying high-risk individuals early, streamline healthcare resource allocation, and reduce costs by preventing complications. Successful models could enhance clinical decision-making, promote early intervention for chronic diseases, and contribute to more efficient, equitable healthcare systems. By tackling this problem, we are helping to directly address gaps in healthcare analytics, offering actionable insights that could save lives and improve global health infrastructure.


## Data Exploration

The WiDS Datathon uses real-world datasets tailored to each year’s challenge. The 2025 Global Challenge uses the Healthy Brain Network (HBN) dataset, which includes functional connectivity matrices (processed via RBC pipelines), P-factor/bifactor analysis, and ADHD-related variables from neuroimaging and behavioral assessments. This dataset integrates neuroimaging data (e.g., connectivity matrices) with clinical/behavioral metrics (e.g., ADHD symptoms, cognitive scores) to explore brain health disparities in women.

Data Exploration and Preprocessing:

Categorical Data-
- We handled null categorical values for ethnicity and education level by reassigning the null values to the values designated in the dictionary for unknown ethnicity and education level, respectively
- Then, we one hot encoded all the categorical values for use in our model!

Numerical Data-
- We calculated correlation values for each of our numerical variables to get a sense of how they might affect one another!

fMRI Data-
- We fit and transformed the fMRI data using a scaler so that the units of measurement would not contrast with the rest of the dataset!


Handling Imbalance: Since the dataset suffers from imbalanced target variables (ADHD diagnosis and gender), we applied SMOTE (Synthetic Minority Over-sampling Technique) separately to each target variable to balance the class distributions. This approach ensures that both ADHD and gender target variables are resampled independently while maintaining alignment between the features and targets.

Feature Selection: After training the Random Forest model, we used feature importance scores to select the top 75% of the most important features. The Random Forest model was able to identify which features (e.g., brain connectivity patterns, socio-demographic information) played a key role in predicting ADHD diagnosis and sex. While brain connectivity data was highly influential, socio-demographic factors like handedness and parenting styles also contributed to the model’s predictions.

Visualizations:

Heatmap of correlated numerical variables
![image](https://github.com/user-attachments/assets/4fc6a9dd-e43c-41b7-8da3-1cf248686045)
Scatterplot showcasing the relation of externalizing and hyperactivity
![image](https://github.com/user-attachments/assets/5e9bfdd3-0b18-449a-99a0-f27114916c82)

## Model Development
Model Selection & Hyperparameter Tuning:
Model Choice: A Random Forest Classifier was chosen due to its robustness, ability to handle complex datasets, and capability to capture both linear and non-linear relationships in the data. Random Forests also provide feature importance scores, which are helpful for identifying key features.

Hyperparameter Tuning: We used RandomizedSearchCV to optimize the hyperparameters of the Random Forest Classifier. The grid search was performed on a range of parameters such as the number of estimators (n_estimators), maximum depth (max_depth), minimum samples for split (min_samples_split), and minimum samples per leaf (min_samples_leaf). This search helps to identify the best combination of parameters for the classifier, which was found to be optimal for predicting ADHD outcomes.

Final Model: After tuning the model, a MultiOutputClassifier was used to handle the multiple target variables (ADHD Outcome and Gender) simultaneously, enabling the model to make predictions for both targets in one go.

## Results & Key Findings

The model achieved an accuracy of 72.41% on the internal test set, demonstrating its ability to predict ADHD diagnosis and sex using a combination of functional MRI data and socio-demographic, emotions, and parenting information

This accuracy reflects the model's ability to correctly predict ADHD outcomes and gender based on the preprocessed data, demonstrating a reasonable level of performance for a classification task on this dataset. Identified correlations between externalizing behaviors and hyperactivity. fMRI data transformation improved model performance, contributing to more accurate ADHD predictions.

## Impact Narrative
The potential clinical impact of this work lies in its ability to aid in the early diagnosis of ADHD, particularly in girls, who often experience delays in diagnosis due to subtler symptoms. With an automated system in place, clinicians could screen individuals more efficiently, facilitating quicker diagnosis and intervention. Additionally, the model's ability to predict both ADHD diagnosis and sex simultaneously could provide valuable information for personalized treatment plans that account for gender differences in symptom presentation and treatment response.

## Next Steps & Future Improvements
Although the model performed well on the training data, its generalization to unseen or out-of-sample data needs further validation. More robust cross-validation and testing on external datasets could improve confidence in the model’s predictive ability.

Potential Improvements:
Including additional neuroimaging data (e.g., fMRI, EEG) could improve the model's accuracy in predicting ADHD. These modalities may offer better insights into the brain activity patterns associated with ADHD, especially in females.

ADHD is a dynamic condition that may exhibit varying symptoms over time. Implementing time series or sequential models could capture temporal patterns in ADHD symptomology, offering better predictions for diagnosis and treatment planning.

Future work could focus on integrating this model with clinical systems, where it could assist healthcare professionals in making more informed decisions about ADHD diagnosis and treatment, ultimately improving patient outcomes.

