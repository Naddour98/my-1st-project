# Modelling Employee Retention using GridsearchCV and XGBoost

## Overview

This project was done at the end of my Google advanced data analytics certificate. The goal was to create a logisitic regression model, a decision tree model, a random forest model, and an XGBoost model to predict why the factors behind employees leacing the company. The project utilized synthetic data for a fictional company called Salifort Motors taken from its HR department. The data is a result from a survey the HR department did for its employees. The random forest model performed best with a 92% recall score and a 95.6% AUC score. Based on the model, the satisfaction level, the number of projects taken on by the employee, the score of their last evaluation, whether they're tenured, and their average monthly working hours were most influential in determind why the employee left.

## Business Understanding

The HR department was tasked with increasing employee retention. Employees receive regular training and it is not porfitable for the company to spend money on employees who will leave. It is important to determine the factors driving employees to leave for the company to capitalize on the training it is giving its employees.

## Data Understanding

The survey [data](https://www.kaggle.com/datasets/mfaisalqureshi/hr-analytics-and-job-prediction?select=HR_comma_sep.csv) from the HR department is syntetic data. It consists of 14,999 rows with 10 features. Our dependent variable **_left_** is **binary**. It is 1 if the employee left and 0 otherwise.

### Features

Variable  |Description |
-----|-----| 
satisfaction_level|Employee-reported job satisfaction level [0&ndash;1]|
last_evaluation|Score of employee's last performance review [0&ndash;1]|
number_project|Number of projects employee contributes to|
average_monthly_hours|Average number of hours employee worked per month|
time_spend_company|How long the employee has been with the company (years)
Work_accident|Whether or not the employee experienced an accident while at work
left|Whether or not the employee left the company
promotion_last_5years|Whether or not the employee was promoted in the last 5 years
Department|The employee's department
salary|The employee's salary (U.S. dollars)

### This is the data distribution of the data:

![image](https://github.com/user-attachments/assets/b4ea8106-8945-442e-b4da-50e3d85ea73a)

3008 duplicate rows were dropped and outliers were dropped _for logisitic regression only_. All variables were reformatted to become numerical or categorical.

## Modelling and Evaluation

A random forest model comprising 500 decision trees was used to determine feature importance in who would leave or not. The below plot shows that the satisfaction level, the number of projects taken on by the employee, the score of their last evaluation, whether they're tenured, and their average monthly working hours were the most important factors in determining an employee that left versus one that didn't. The overall model performed with 98.1% accuracy, 96.4% precision, 92% recall, and 95.6% auc.

### Feature Importance

![image](https://github.com/user-attachments/assets/4e4c947f-07c2-4519-b55e-abd4b383ff55)

## Conclusion

This model can benefit the company to identify potential employees who want to leave the company through frequent surveys done by HR. Certain anomalies may warrant additional investigation, however they are most likely due to the data being synthetic.
