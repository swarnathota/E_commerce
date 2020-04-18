# Gender prediction based on purchases

**Objective**

Predicting the gender of the customer based on purchases. This sheds light on behavior of male and female users. 

## **Data Acqisition:**

-  This project hasbeen done as a participant in janata hackaton conducted by "Analytics Vidya" as support of covid lockdown.

- Train and test data have been provided by "Analytics Vidya".

## **Feature engineering**

Features were generated from products and time stamps :

- Total_number of products per session

- Product, categories and sub catetegories were generated.

- Total time per session, Hour of the day and Weekdays extracted from time stamps.

## **Exploratory data analysis:** 

- who bought most of the products or who shopped the most male or female?

- Visualize purchase patterns such as who shopped the most in any weekday or any hour of the day?

- Total_time  vs Total Number of products?

- Who bought most number products and how much time they took per session ?

## Outlier detection:

- Using describe() method in pandas I could verify there is an anomoly in the data. that could be real values or the outliers. 

- By Box and whisker plots could confirm the data points were away from the actual data. 

- To further verify I used IsolationForest algorithm and plotted outliers. I further verified how was the purchase pattern in the outliers, which is completely off from the rest of the data. 

- I removed those outliers and proceeded for the modeling.

## **Modeling**

- It is a classification model as the out is predicting male or female based on purchase of products. Sample is imbalanced with 1:3 ratio of male to female  respectively. 

- Initially logistic regression  by giving class weights used for classes. Although accuracy score of 0.84 this model could  gave AUC scores 0.821 from ROC_AUC curve. 
- To get better performance sample is imbalanced I used SMOTE to OVER SAMPLE the minority class. It gave same result as Logistic regression with out over sampling.
- I used XGBoost to get better performance. Using GridSearchCV found best parameters for XGB.  An accuracy score of 0.86 and AUC score of  0.834 from ROC_AUC curve and gave better confusion matrix.

## **Prediction:**

Finally gender was predicted on test data set provided with 0.78 score.



