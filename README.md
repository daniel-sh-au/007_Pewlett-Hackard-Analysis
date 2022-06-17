# Module 7: Employee Database with SQL

## Overview of the Analysis

### Purpose
To prepare for the retirement of baby boomers at Pewlett Hackard, an analysis was performed to determine the number of retiring employees by title and to identify the employees eligible for the mentorship program which will assist in the transition. 

### Resources
* pgAdmin, PostgreSQL
* Entity Relationship Diagram (ERD): [EmployeeDB.png](https://github.com/daniel-sh-au/UofT_DataBC_Module07_Pewlett-Hackard-Analysis/blob/main/Queries/EmployeeDB.png)
* Challenge Code: [Employee_Database_Challenge.sql](https://github.com/daniel-sh-au/UofT_DataBC_Module07_Pewlett-Hackard-Analysis/blob/main/Queries/Employee_Database_Challenge.sql)
* Results: [retirement_titles.csv](https://github.com/daniel-sh-au/UofT_DataBC_Module07_Pewlett-Hackard-Analysis/blob/main/Data/retirement_titles.csv), [unique_titles.csv](https://github.com/daniel-sh-au/UofT_DataBC_Module07_Pewlett-Hackard-Analysis/blob/main/Data/unique_titles.csv), [retiring_titles.csv](https://github.com/daniel-sh-au/UofT_DataBC_Module07_Pewlett-Hackard-Analysis/blob/main/Data/retiring_titles.csv), [mentorship_eligibility.csv](https://github.com/daniel-sh-au/UofT_DataBC_Module07_Pewlett-Hackard-Analysis/blob/main/Data/mentorship_eligibility.csv)

## Results
The tables below show the number of current employees in each title and the number of retiring employees in each title. The query was modified to include the percentage of employees in each title. 

| Current Employees Titles | Retiring Employees Titles|
| ------------------------ | ------------------------ |
| ![current_employees_titles_with_percentage.png](https://github.com/daniel-sh-au/UofT_DataBC_Module07_Pewlett-Hackard-Analysis/blob/main/Resources/current_employees_titles_with_percentage.PNG) | ![retiring_titles_with_percentage.png](https://github.com/daniel-sh-au/UofT_DataBC_Module07_Pewlett-Hackard-Analysis/blob/main/Resources/retiring_titles_with_percentage.png)

* In the table, we can see that the majority of those retiring are in senior positions, specifically Senior Engineer (35.77%) and Senior Staff (34.40%). Other retiring employees include Engineers (12.81%), Staff (10.54%), Technique Leader (4.97%), Assistant Engineers (1.50%), and Managers (0.0028%). 
* Comparing the current employee and retiring employee tables above, we can see similar trends in percentages. For example, Senior Engineers make up 35.79% of current employees but they also make up 35.77% of retiring employees. This demonstrates that there are no abnormalities in the retirement as each title should be losing approximately the same percentage of employees. This was calculated in the table below. It was found that each title was losing about 30.00% of their employees with the exception of Manager. 
  ![retiring_current_count_percentage.png](https://github.com/daniel-sh-au/UofT_DataBC_Module07_Pewlett-Hackard-Analysis/blob/main/Resources/retiring_current_count_percentage.png)
*
data as each individual title is not losing a significant percentage of their employees. 

* retiring titles png, few managers
* 


## Summary
How many roles will need to be filled as the "silver tsunami" begins to make an impact?
Are there enough qualified, retirement-ready employees in the departments to mentor the next generation of Pewlett Hackard employees?

