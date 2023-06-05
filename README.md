# Logistic Regresion and Tree-based model to provied data-driven suggestions fot HR of Salifort Motors

## Project Overview
The goal of this project was to create a logistic regression and tree-based model to predict if a employee would leave Salifort Motors. 

The logisitc regresion model performed with 80% precision, 82% recall, f1-score 81% (all weighted average) and 82% accuracy. 

Then the random forest was selecting because perform slightly better than decision tree model, the random forest model perfomed with 93.4% AUC, 86.4% accuracy, 88.9% recall, 89.2% f1-score, 89.4% precision, determining most important features after doing a feature engineering process. Based on this, last evaluation doing by HR, number of projects assign to each employee, the tenure of each emplooye in the company and if the employee was overworked were most influential in determining if employee would leave or not the company.


## Buisness understanding

The HR department at Salifort Motors wants to take some initiatives to improve employee satisfaction levels at the company. They collected data from employees, but now they don’t know what to do with it. They have the following question: what’s likely to make the employee leave the company?

The main goal on this project is to analyze the data collected by the HR department and to build a model that predicts whether or not an employee will leave the company.

If the model can predict employees likely to quit, it might be possible to identify factors that contribute to their leaving. Because it is time-consuming and expensive to find, interview, and hire new employees, increasing employee retention will be beneficial to the company.

## Data Understanding

The HR of Salifort data came from [Kaggle](https://www.kaggle.com/datasets/mfaisalqureshi/hr-analytics-and-job-prediction?select=HR_comma_sep.csv). This dataset contains 15000 rows and 10 columns for the variables listed below

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

Using a random forest model to determine feature importance in who employees would leave or stay in the company. The below plot shows that `last_evaluation`, `number_project`, `tenure` and `overworked` were the most important factors in determine if employees leave or stay. The overall model performed on test set with 93.4% AUC, 96.4% Accuracy, 88.9% Recall, 89.2% f1-socre and 89.4% precision.
![Random Forest most importance features](https://github.com/CameVibes/Project-SM/assets/134762914/a81abab6-4ace-4d01-9d1f-4e87384258bd)

Using a decision tree model to determine feature importance in who employees would leave or stay in the company. The below plot shows that `number_project`, `last_evaluation`, `tenure` and `overworked` were the most important factors in determine if employees leave or stay. The decision tree model sighltly underperformed the decision tree model.
![Tree Model most importance features](https://github.com/CameVibes/Project-SM/assets/134762914/6ee44d6b-4b54-4b5c-bd3d-c1ac2262b778)


## Conclusions

The following recomendations could be present to the stakeholders, this recomendations are based on the feature importances of the Random Forest Model: (`last_evaluation`, `number_project`, `tenure`, `overworked`), to retain employees:

* High evaluation scores should not be reserved for employees who work 175+ hours per month. Consider to implement a proportional scale for rewarding employees based on their level of contibution an effort. 
* Set a limit on the number of projects that employees can work on. 
* Conduct a further investigation about why four-year tenure employees are so dissatisfied. Consider promoting employees who have been in the company for atleast four years.
* Reward employees for working longer hours, if the expectations around workload and time off aren't explicit, make them clear

**Next Steps**

It could be prudent to consider how predictions change when `last_evaluation` is dropping from the data, it may be justified in the context about data leakage. Because it's possible that evaluation's aren't performed very frequently, in wich case would be useful to be able to predict employee retention without this feature.
