# Heart Disease Prediction Project

 Every year, a large number of individuals lose their lives due to heart disease. 
The goal of this project is to use machine learning techniques and medical data analysis 
 to uncover hidden patterns and relationships among features of individuals 
 who have suffered from heart disease. 
 This will help us predict the disease with higher accuracy and contribute to early diagnosis.

## Project Objectives:

 - Identify important features related to heart disease.
 - Utilize machine learning models to analyze and predict heart disease.
 - Develop a model that can accurately identify individuals at risk of heart disease.

## Techniques Used:

# This project employs the following two machine learning algorithms:

 - Logistic Regression: To model the probability of heart disease based on input data.
 - Naive Bayes: For classification and data analysis under the assumption of feature independence.




## How the  logistic regression Model Works for Predicting Heart Disease



In logistic regression, our goal is to model the probability of a specific event occurring. In this technique, we aim to predict a categorical variable that has only two possible outcomes (e.g., Yes or No, 0 or 1). This prediction is based on several independent variables, which can be either continuous or categorical. Simply put, logistic regression helps us estimate the likelihood of an event happening using existing data, and then classify the results in a binary fashion.




The effectiveness of a logistic regression model is heavily dependent on the choice of features used for prediction. Selecting relevant features is crucial, as the quality of the model's predictions is directly influenced by these variables. If too many irrelevant or redundant features are included, the model may become overly complex and less effective at making accurate predictions. Conversely, choosing the right set of features helps the model to better identify patterns and relationships in the data, leading to more reliable predictions.

In summary, logistic regression is a valuable tool for binary classification problems, such as predicting heart disease. By carefully selecting and optimizing the features used in the model, we can enhance its accuracy and overall performance in predicting patient outcomes.



## Feature Selection

## ANOVA and Tukey HSD Analysis

Below are the results of the ANOVA and Tukey HSD tests for various variables:

| **Variable** | **ANOVA p-value** | **Significant** | **Tukey HSD Details**                          |
|--------------|-------------------|-----------------|------------------------------------------------|
| age          | 7.52e-05          | Yes             | Multiple Comparison of Means - Tukey HSD, FWER... |
| trestbps     | 1.15e-02          | Yes             | Multiple Comparison of Means - Tukey HSD, FWER... |
| chol         | 1.39e-01          | No              | None                                           |
| thalach      | 1.70e-14          | Yes             | Multiple Comparison of Means - Tukey HSD, FWER... |
| oldpeak      | 4.09e-15          | Yes             | Multiple Comparison of Means - Tukey HSD, FWER... |



In this section of the project, Analysis of Variance (ANOVA) is used to examine the relationship between continuous variables (such as age, resting blood pressure, cholesterol, maximum heart rate, and ST depression) and the categorical dependent variable (target).

The table below shows the results of the ANOVA, indicating whether there are significant differences in the means of these continuous variables across the different categories of the target variable.

The p-value represents the probability that the observed differences are due to chance. If the p-value is less than 0.05, the variable is considered to have a significant difference between groups (the "Significant" column is marked as "True").

For variables that show significant differences (such as "age," "trestbps," "thalach," and "oldpeak"), the Tukey's HSD test is used to determine exactly which groups differ from each other. The Tukey test performs pairwise comparisons with precision and helps prevent statistical errors.

For a variable like "chol", where the p-value is greater than 0.05, no significant difference was observed, and thus, the Tukey test is not necessary.






 ## Chi-square

 | Variable   | Chi-square value | P-value         |
|------------|------------------|-----------------|
| sex        | 22.717227         | 1.876778e-06    |
| cp         | 81.686428         | 1.334304e-17    |
| fbs        | 0.106273          | 7.444281e-01    |
| restecg    | 10.023092         | 6.660599e-03    |
| exang      | 55.944550         | 7.454409e-14    |
| slope      | 47.506897         | 4.830682e-11    |
| ca         | 74.366631         | 2.712470e-15    |
| thal       | 85.303740         | 2.233351e-18    |
| target     | 298.981398        | 5.491510e-67    |




In this section of the project, the Chi-square test is used to examine the relationship between the categorical dependent variable (target) and several categorical independent variables. This test helps us determine whether there is a significant difference in the distribution of data across the different groups of independent variables.

For variables such as sex, cp (chest pain type), exang (exercise-induced angina), slope, ca (number of major vessels), and thal, the P-value is less than 0.05, indicating a significant relationship between these variables and the target.

For the variable fbs (fasting blood sugar), the P-value is 0.744, showing no significant relationship between this variable and the target.

The very small P-value for the target variable (5.491510e-67) indicates a highly significant difference among the groups of this variable.

These results demonstrate that some categorical independent variables, such as cp, thal, and ca, have a significant relationship with the dependent variable, while others, like fbs, do not have a notable impact.





## Training the model




The allocation of training and test data ratios has a significant impact on the performance of our model. To achieve a more accurate evaluation, we test various ratios between the training and test data and examine the model's accuracy for each to identify the optimal combination.


Training Ratio: 50% | Accuracy: 82.24%

Training Ratio: 60% | Accuracy: 81.97%

Training Ratio: 70% | Accuracy: 82.42%

Training Ratio: 80% | Accuracy: 86.89%

Training Ratio: 90% | Accuracy: 83.87%



![traaing](https://github.com/user-attachments/assets/ac7a8f01-6bab-47b3-8d80-c3e109d90294)


Based on the above chart, the 80% training data and 20% test data ratio has been selected as the optimal choice, as the model shows the highest accuracy of 86.89% with this ratio. Choosing this ratio helps us achieve the best possible performance from our model.













## How the Naive Bayes Model Works for Predicting Heart Disease

In this model, we start by calculating the probability that an individual has or does not have heart disease. These are considered as initial guesses (referred to as **prior probabilities**). Once we have these prior probabilities, we proceed to calculate the probability of an individual with specific features, such as age, blood pressure, and other characteristics, having heart disease.

### Here's how the process works:

1. **Prior Probability**: First, we consider the probability that an individual either has or does not have heart disease.

2. **Calculating Probability for Each Feature**: For each feature (such as age or cholesterol level), we calculate the likelihood of that feature appearing in individuals with and without heart disease. For example, we calculate the probability that a person with a certain blood pressure level has heart disease.

3. **Combining Probabilities**: Then, we combine these probabilities (by multiplying the probabilities of each feature). This means for each feature, such as age, blood pressure, or cholesterol, we calculate the probability of having heart disease, and then combine them to reach an overall result.

4. **Final Prediction**: Finally, we see which condition (having or not having heart disease) has the highest probability, and we select that as the final prediction.

For example, if an individual has high cholesterol and high blood pressure, we calculate the probability that they have heart disease based on these features and make a final prediction by also considering other features like age and gender.

It's important to note that the Naive Bayes model assumes that features are independent of each other, meaning, for example, that cholesterol level does not affect age. Although this assumption is not always true in reality, the model still performs well and is computationally efficient.

### Model Performance Metrics

| Metric     | Score     |
|------------|-----------|
| Accuracy   | 0.815789  |
| Precision  | 0.775510  |
| Recall     | 0.926829  |
| F1 Score   | 0.844444  |


Our model performs well in identifying positive cases, but in some instances, it incorrectly predicts healthy individuals as having the disease.


### Confusion Matrix

![confusion_matrix_plot](https://github.com/user-attachments/assets/bf906a2d-232b-4e12-894c-1c20e36a8776)

There are 11 false positives where the model incorrectly predicted healthy individuals as having the disease. This is a notable amount and should be further investigated. There are only 3 false negatives, indicating that the model has performed well in identifying diseased individuals.








