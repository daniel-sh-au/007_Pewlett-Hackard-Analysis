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
* Comparing the current employee and retiring employee tables above, we can see similar trends in percentages. For example, Senior Engineers make up 35.79% of current employees but they also make up 35.77% of retiring employees. This demonstrates that there are no abnormalities in the retirement data as each title should be losing approximately the same percentage of employees. This was calculated in the table below. It was found that each title was losing about 30.00% of their employees with the exception of the Manager role. 
  ![retiring_current_count_percentage.png](https://github.com/daniel-sh-au/UofT_DataBC_Module07_Pewlett-Hackard-Analysis/blob/main/Resources/retiring_current_count_percentage.PNG)

| Mentorship Eligible Employees Titles |
| ------------------------------------ |
|![mentorship_eligibility_titles.png](https://github.com/daniel-sh-au/UofT_DataBC_Module07_Pewlett-Hackard-Analysis/blob/main/Resources/mentorship_eligibility_titles.png)|
* The table above displays the number of mentorship eligible employees in each title. In contrast to the Current/Retiring Employees Titles tables above, possible mentors are mostly in the Senior Staff or Engineer role. This could be a potential issue for roles such as Senior Engineer where there may by an inadequate amount of Senior Engineer mentors to support the "silver tsunami". A possible solution could be to increase the mentorship criteria from just employees born in 1965. 
* Another major observation was realizing how few managers roles exist at Pewlett Hackard. Despite only 22.22% of managers retiring soon, this is significant considering there are no eligible manager mentors. With so many employees retiring, this could be a great opportunity for Pewlett Hackard to determine why some of the more senior employees were not given the opportunity to become managers themselves. Furthermore, this could be an opportunity for the company to hire more managers to improve the current imbalance of roles. 

## Summary
With the retirement of baby boomers at Pewlett Hackard, 72458 employees will need to be hired to make an impact. This was calculated from the count of all soon to be retired employees born between 01/01/1952 and 12/31/1955. As this is a significant number of employees (~30% of the company), the mentorship program will provide some assistance with this transition. Currently, 1549 employees are eligible for the mentorship program. This number is approximately 2.14% of the total number of employees that must be rehired. This is clearly not enough employees to mentor the next generation of Pewlett Hackard workers. A solution for this problem could be to expand the eligibility criteria in becoming a mentor; Currently, only employees born in 1965 are qualified. This eligibility criteria could be expanded to allow for employees born from 1962-1965 to become mentors. Additionally, employees with longer years of service should also be considered eligible in becoming mentors. Another problem exists in the ratio of Senior Engineer mentors to Senior Engineer retiring employees, which is approximately 1:105. This is a major complication as 1 Senior Engineer could not possibly mentor 105 new Senior Engineers. In addition to expanding the mentorship criteria, it might beneficial to promote some of the qualified Engineers to Senior Engineers. 

**Additional Queries**
```
-- Count of employees retiring (72458)
SELECT COUNT (emp_no) 
FROM unique_titles;

-- Count of employees eligible for mentorship (1549)
SELECT COUNT(emp_no) 
FROM mentorship_eligibility;

-- Determine number of current employees of each title with percentage
SELECT COUNT(title), ROUND(COUNT(*) * 100.0 / (SELECT COUNT(*) FROM titles),4) as "percentage", title
FROM titles
WHERE to_date = '9999-01-01'
GROUP BY title
ORDER BY COUNT(title) DESC;

-- Addition to retiring_title query to include percentage
SELECT COUNT(title), ROUND(COUNT(*) * 100.0 / (SELECT COUNT(*) FROM unique_titles),4) as "percentage", title
FROM unique_titles
GROUP BY title
ORDER BY COUNT(title) DESC;

-- Determine number of Mentorship Eligible employees in each title
SELECT COUNT(title), title
FROM mentorship_eligibility
GROUP BY title
ORDER BY COUNT(title) DESC;
```
