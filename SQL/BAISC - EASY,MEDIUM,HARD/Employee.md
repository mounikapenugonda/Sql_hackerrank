### Employee details follow:

Input Format:::
            The STUDENTS table is described as follows:
| Column | Type|
| :---:  |  :---:|
| ID | Integer |
| Name | String |
| Marks | Integer|

The name column only contains uppercase (A-Z) and lowercase (a-z) letters. 
where employee_id is an employee's ID number, name is their name, months is the total number of months they've been working for the company, and salary is their 
monthly salary.

### Higher Than 75 Marks
Q1.Query the Name of any student in STUDENTS who scored higher than  Marks. Order your output by the last three characters of each name. If two or more students
both have names ending in the same last three characters (i.e.: Bobby, Robby, etc.), secondary sort them by ascending ID.

Sample Input :: 
| ID | Name | Marks |
| :--:|:--: | :--: |
| 1 | Ashley | 81 |
| 2 | Samantha | 75 |
| 3 | Julia | 76 |
| 4 | Belvet | 84 |

Sample Output : Ashley, Julia, Belvet
Explanation :: 

Only Ashley, Julia, and Belvet have Marks > . If you look at the last three characters of each of their names, there are no duplicates and 'ley' < 'lia' < 'vet'.
    
    Solution 1: SELECT NAME FROM STUDENTS WHERE MARKS > 75 ORDER BY SUBSTR(NAME, -3) , ID ;    
### Employee Names
Q2.Write a query that prints a list of employee names (i.e.: the name attribute) from the Employee table in alphabetical order.
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
Sample Output :: Angela, Bonnie, Frank, Joe, Kimberly, Lisa, Michael, Patrick, Rose, Todd

    Solution 1: SELECT NAME FROM EMPLOYEE ORDER BY NAME;
    Solution 2: SELECT NAME FROM EMPLOYEE ORDER BY NAME ASC;
### Employee Salaries
Q3.Write a query that prints a list of employee names (i.e.: the name attribute) for employees in Employee having a salary greater than $ 2000 per month who have been 
employees for less than 10 months. Sort your result by ascending employee_id. 
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
Sample Output ::: Angela, Michael, Todd, Joe
Explanation ::

Angela has been an employee for 1 month and earns $3443 per month.
Michael has been an employee for 6 months and earns $2017 per month.
Todd has been an employee for 5 months and earns $3396 per month.
Joe has been an employee for 9 months and earns $3573 per month.
We order our output by ascending employee_id.

    Solution : SELECT NAME FROM EMPLOYEE WHERE SALARY > 2000 AND MONTHS < 10 ORDER BY EMPLOYEE_ID ASC;
### Top Earners
Q3.We define an employee's total earnings to be their monthly salary * months worked, and the maximum total earnings to be the maximum total earnings for any employee in the Employee table. Write a query to find the maximum total earnings for all employees as well as the total number of employees who have maximum total earnings. Then print these values as 2 space-separated integers.
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
