# Logistic Regression and Tree-based model to provied data-driven suggestions for HR of Salifort Motors

## Project Overview

The objective of this project was to develop a logistic regression and a tree-based model to predict if an employee would leave Salifort Motors.

The logistic regression model performed with 80% precision, 82% recall, an f1-score of 81% (all weighted averages), and 82% accuracy.

Next, the random forest model was selected because it performed slightly better than the decision tree model. The random forest model achieved a 93.4% AUC, 86.4% accuracy, 88.9% recall, 89.2% f1-score, and 89.4% precision, determining the most important features after undergoing a feature engineering process. According to this, the last evaluation done by HR, the number of projects assigned to each employee, the tenure of each employee in the company, and whether the employee was overworked were the most influential in determining if an employee would leave the company or not.

## Buisness understanding

The HR department at Salifort Motors intends to initiate measures to enhance employee satisfaction levels within the company. They collected data from employees but are uncertain about the next steps. Their primary question is: what is likely to make an employee leave the company?

The main aim of this project is to analyze the data collected by the HR department and to build a model that predicts whether or not an employee will leave the company.

If the model can predict which employees are likely to quit, it might be possible to identify factors that contribute to their decision to leave. Since finding, interviewing, and hiring new employees is both time-consuming and expensive, increasing employee retention will be beneficial for the company.

## Data Understanding

The HR of Salifort data came from [Kaggle](https://www.kaggle.com/datasets/mfaisalqureshi/hr-analytics-and-job-prediction?select=HR_comma_sep.csv). This dataset contains 15000 rows and 10 columns for the variables listed below:

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

## Modeling and Evaluation

Using a random forest model to determine feature importance in who employees would leave or stay in the company. The below plot shows that `last_evaluation`, `number_project`, `tenure` and `overworked` were the most important factors in determine if employees leave or stay. The overall model performed on test set with a 93.4% AUC, 96.4% Accuracy, 88.9% Recall, 89.2% f1-socre and 89.4% precision.

![Random Forest most importance features](https://github.com/CameVibes/Project-SM/assets/134762914/a81abab6-4ace-4d01-9d1f-4e87384258bd)


Using a decision tree model to determine feature importance in who employees would leave or stay in the company. The below plot shows that `number_project`, `last_evaluation`, `tenure` and `overworked` were the most important factors in determine if employees leave or stay. The decision tree model sighltly underperformed the decision tree model.

![Tree Model most importance features](https://github.com/CameVibes/Project-SM/assets/134762914/6ee44d6b-4b54-4b5c-bd3d-c1ac2262b778)


## Conclusions

Based on the feature importance of the Random Forest Model (`last_evaluation`, `number_project`, `tenure`, `overworked`), the following recommendations could be presented to the stakeholders to improve employee retention:

* High evaluation scores shouldn't be exclusive to employees who work 175+ hours per month. Implementing a proportional scale to reward employees based on their contributions and efforts could be considered. 
* There should be a limit to the number of projects that employees can be assigned.
* Further investigations should be conducted to understand why employees with a four-year tenure are notably dissatisfied. Consider promoting employees who have been with the company for at least four years.
* Employees who work longer hours should be rewarded. If the expectations regarding workload and time off are not explicitly defined, it is crucial to make them clear.

**Next Steps**

In future analysis, it would be interesting to see how predictions are affected when the  `last_evaluation` factor is dropped from the data due to potential data leakage. It's plausible that evaluations aren't conducted frequently. In such cases, predicting employee retention without this feature could be useful.
