# WIDS Team 13
### Tiffney Aina, Wei Ding, Erynn Gutierrez, Ivi Fung

Tiffany (Team Lead): https://github.com/tiffaina

Wei (Programming Lead): https://github.com/Wei0015

Erynn (Data Cleaning and Visualization): https://github.com/Erynn-Gutierrez

Ivi (Data Cleaning and Visualization): https://github.com/MostEsteemedFungus

## Project Overview
The goal of this project to build a model to predict both an individual’s sex and their ADHD diagnosis using functional brain imaging data of children and adolescents and their socio-demographic, emotions, and parenting information.

Target Variables
ADHD_Outcome: Type of Diagnosis (0=Other/None, 1=ADHD)
Sex_F: Sex of participant (0=Male, 1=Female)

We used a multioutput classifier to achieve an accuracy score of 0.72411.

## Setup and Execution
After downloading the data and uploading it to your Google Drive, run each of the code blocks in the script in succession.
NB: You might need to update the second block to reflect the actual location of the data in your Google Drive.

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

Visualizations:

Heatmap of correlated numerical variables
![image](https://github.com/user-attachments/assets/4fc6a9dd-e43c-41b7-8da3-1cf248686045)
Scatterplot showcasing the relation of externalizing and hyperactivity
![image](https://github.com/user-attachments/assets/5e9bfdd3-0b18-449a-99a0-f27114916c82)

## Model Development

## Results and Key Findings

## Impact Narrative

## Next Steps and Future Improvements




