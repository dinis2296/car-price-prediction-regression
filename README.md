# Breast Cancer Classification

This project uses machine learning models to classify tumors as malignant or benign using clinical features derived from medical imaging.

## Objective 

The goal is to build a reliable classification model with a strong focus on recall, minimizing false negatives (i.e., malignant tumors incorrectly classified as benign), which is critical in medical diagnosis.

## Models Used
- Logistic Regression
- KNN
- Random Forest
- Gradient Boosting

## Model Results

![Model_Results](images/model_results_wKNN.png)

## Key Insights
- The strong performance of Logistic Regression suggests that the relationship between features and the target variable is largely linear.
- Although features such as perimeter_mean and perimeter_worst show strong separation in isolation, their importance is reduced in the model due to multicollinearity with other features like radius and area.
Features such as radius_se and concave points_mean show strong influence, likely acting as representatives of broader feature groups (e.g., tumor size and shape).
- The model demonstrates strong potential for assisting in early detection of malignant tumors.

## Limitations

- Relatively small dataset
- Presence of multicollinearity between features
