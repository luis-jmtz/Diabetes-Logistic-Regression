# Diabetes Dataset: Data Cleaning and Preliminary Analysis

## Project Overview
This project involves the data cleaning and preliminary analysis of the Diabetes Dataset from the National Institute of Diabetes and Digestive and Kidney Diseases. The objective of the dataset is to diagnostically predict whether a patient has diabetes based on diagnostic measurements. All patients in the dataset are females at least 21 years old of Pima Indian heritage.

The goal of this analysis was to prepare the data for a Logistic Regression model. However, during the data exploration phase, significant issues with missing values were identified, which impacted the usability of the dataset for predictive modeling.

## Dataset Attributes
- **Pregnancies**: Number of pregnancies
- **Glucose**: Glucose level in blood
- **BloodPressure**: Blood pressure measurement
- **SkinThickness**: Thickness of the skin
- **Insulin**: Insulin level in blood
- **BMI**: Body mass index
- **DiabetesPedigreeFunction**: Diabetes percentage
- **Age**: Age of the patient
- **Outcome**: Final result (1 = Yes, 0 = No)

## Data Cleaning Process

### Initial Data Inspection
The dataset contains 768 rows and 9 columns. Initial checks revealed no null values or duplicated rows based on standard missing value detection methods.

### Identification of Implied Missing Values
Further analysis uncovered that several medical measurements (Glucose, BloodPressure, SkinThickness, Insulin, BMI) contain zeros, which are biologically implausible and likely represent missing data:

- **Glucose**: 5 zero values
- **BloodPressure**: 35 zero values  
- **SkinThickness**: 227 zero values
- **Insulin**: 374 zero values
- **BMI**: 11 zero values

### Impact on Data Usability
When rows containing any zero values in these medical measurements were removed, the dataset was reduced to 392 rows (approximately 51% of the original data). This significant data loss would substantially limit the effectiveness of any predictive model built from this dataset.


## Conclusion
The dataset contains a substantial number of missing values represented as zeros in critical medical measurement columns. The high percentage of missing data (approximately 49% of rows contain at least one implausible zero value) significantly impacts the dataset's utility for building a reliable Logistic Regression model.

Without appropriate imputation strategies or access to the complete dataset, the predictive performance of any model trained on this data would be severely compromised. Further work would require either:
1. Obtaining a more complete version of the dataset
2. Implementing sophisticated imputation techniques tailored to medical data
3. Using alternative datasets with more complete medical measurements

## Technologies Used
- Python
- Pandas for data manipulation
- Jupyter Notebook for interactive analysis

## Files
- `diabetes.csv`: Original dataset
- Data cleaning and analysis notebook

## Limitations
The primary limitation identified is the high volume of missing data in key predictive features, which prevents the development of a robust predictive model using this dataset in its current form.