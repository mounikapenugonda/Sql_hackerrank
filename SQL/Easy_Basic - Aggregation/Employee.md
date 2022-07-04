### EMPLOYEES TABLE 
Input Format - The EMPLOYEES table is described as follows:

| Column | Type|
| -- |--|
| ID | Integer|
| Name | String|
| Salary | Integer|

Note: Salary is per month.
Constraints : 1000 < Salary <10 power 5.
Sample Input

| ID | Name | Salary |
| -- | -- | -- |
| 1 | Kristeen | 1420 |
| 2 | Ashley | 2006 |
| 3 | Julia | 2210 |
| 4 | Maria | 3000 |

### The Blunder
Q1. Samantha was tasked with calculating the average monthly salaries for all employees in the EMPLOYEES table, but did not realize her keyboard's  key was broken until after completing the calculation. She wants your help finding the difference between her miscalculation (using salaries with any zeros removed), and the actual average salary.

Write a query calculating the amount of error (i.e.: Actual - miscalculated average monthly salaries), and round it up to the next integer.
Sample Output ::: 2061
Explanation :::: The table below shows the salaries without zeros as they were entered by Samantha:

| ID | Name | Salary |
| -- | -- | -- |
| 1 | Kristeen | 142 |
| 2 | Ashley | 26 |
| 3 | Julia | 221 |
| 4 | Maria | 3 |

Samantha computes an average salary of 98.00. The actual average salary is 2159.00.
The resulting error between the two calculations is 2159.00 - 98.00 =2061.00 . Since it is equal to the integer 2061, it does not get rounded up.

    ANS : SELECT CEIL(AVG(SALARY) - AVG(REPLACE(SALARY,'0',''))) FROM EMPLOYEES;
    explanation - I am  using ceil here bcz it will CEILING rounds up, while ROUND rounds number in standard way.
### Top Earners
Q2.We define an employee's total earnings to be their monthly salary * months worked, and the maximum total earnings to be the maximum total earnings for any employee in the Employee table. Write a query to find the maximum total earnings for all employees as well as the total number of employees who have maximum total earnings. Then print these values as 2 space-separated integers.

Sample Input
| employee_id | name | months | salary |
| :--:|:--: | :--: |  :--: |
| 12228 | Rose | 15 |  1968|
| 33645 | Angela | 1 |  3443|
| 45692 | Frank | 17 |  1608|
| 56118 | Patric | 7 |  1345|
| 59725 | Lisa | 11 |  2330|
| 74197 | Kimberly | 16 |  4372|
| 78454 | Bonnie | 8 |  1771|
| 83565 | Michel | 6 |  2017|
| 98607 | Todd | 5 |  3396|
| 99989 | Joe | 9 |  3573| 

Sample Output ::: 69952 1
Explanation :: The table and earnings data is depicted in the following diagram:   

| employee_id | name | months | salary | earnings |
| :--:|:--: | :--: |  :--: | :--:|
| 12228 | Rose | 15 |  1968| 29520 |
| 33645 | Angela | 1 |  3443|  3443 |
| 45692 | Frank | 17 |  1608| 27336 |
| 56118 | Patric | 7 |  1345| 9415 |
| 59725 | Lisa | 11 |  2330|  25630 |
| 74197 | Kimberly | 16 |  4372| 69952 |
| 78454 | Bonnie | 8 |  1771| 14168 |
| 83565 | Michel | 6 |  2017| 12102 |
| 98607 | Todd | 5 |  3396| 16980 |
| 99989 | Joe | 9 |  3573|  32157 |
The maximum earnings value is 69952. The only employee with earnings = 69952  is Kimberly, so we print the maximum earnings value (69952) and a count of the number of employees who have earned $69952 (which is 1) as two space-separated values.

    Solution :SELECT MAX(salary * months), COUNT(salary * months) FROM EMPLOYEE where (salary * months) = (select max(salary * months) from employee);

