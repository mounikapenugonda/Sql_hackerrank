### Revising the Select Query -|
Q1: Query all columns for all American cities in the CITY table with populations larger than 100000. The CountryCode for America is USA.

The CITY table is described as follows:
| FIELD | TYPE |
| :---: | :---: |
| ID | NUMBER |
| NAME | VARCHAR(20) |
| COUNTRYCODE | VARCHAR(20) |
| DISTRICT | VARCHAR(20) |
|POPULATION | NUMBER |

    Solution : SELECT * FROM CITY WHERE POPULATION > 100000 AND COUNTRYCODE = "USA";
    
### Revising the Select Query - ||
Q2.Query the NAME field for all American cities in the CITY table with populations larger than 120000. The CountryCode for America is USA.

The CITY table is described as follows:
| FIELD | TYPE |
| :---: | :---: |
| ID | NUMBER |
| NAME | VARCHAR(20) |
| COUNTRYCODE | VARCHAR(20) |
| DISTRICT | VARCHAR(20) |
|POPULATION | NUMBER |

    Solution : SELECT NAME FROM CITY WHERE POPULATION > 120000 AND COUNTRYCODE = "USA";
    
### Select All
Q3. Query all columns (attributes) for every row in the CITY table.

The CITY table is described as follows:
| FIELD | TYPE |
| :---: | :---: |
| ID | NUMBER |
| NAME | VARCHAR(20) |
| COUNTRYCODE | VARCHAR(20) |
| DISTRICT | VARCHAR(20) |
|POPULATION | NUMBER |

    Solution : SELECT * FROM CITY;
    
 ### Select by ID
 Q4. Query all columns for a city in CITY with the ID 1661.

The CITY table is described as follows:
| FIELD | TYPE |
| :---: | :---: |
| ID | NUMBER |
| NAME | VARCHAR(20) |
| COUNTRYCODE | VARCHAR(20) |
| DISTRICT | VARCHAR(20) |
|POPULATION | NUMBER |

    Solution : SELECT * FROM CITY WHERE ID = 1661;
    
### JAPANESE Cities Attributes
Q5. Query all attributes of every Japanese city in the CITY table. The COUNTRYCODE for Japan is JPN.

The CITY table is described as follows:
The CITY table is described as follows:
| FIELD | TYPE |
| :---: | :---: |
| ID | NUMBER |
| NAME | VARCHAR(20) |
| COUNTRYCODE | VARCHAR(20) |
| DISTRICT | VARCHAR(20) |
|POPULATION | NUMBER |

    Solution : SELECT * FROM CITY WHERE COUNTRYCODE = "JPN";
    
### JAPANESE Cities NAMES
Q6. Query the names of all the Japanese cities in the CITY table. The COUNTRYCODE for Japan is JPN.
The CITY table is described as follows:
| FIELD | TYPE |
| :---: | :---: |
| ID | NUMBER |
| NAME | VARCHAR(20) |
| COUNTRYCODE | VARCHAR(20) |
| DISTRICT | VARCHAR(20) |
|POPULATION | NUMBER |

    Solution : SELECT NAME FROM CITY WHERE COUNTRYCODE = "JPN";

### Higher Than 75 Marks
Q17.Query the Name of any student in STUDENTS who scored higher than  Marks. Order your output by the last three characters of each name. If two or more students both have names ending in the same last three characters (i.e.: Bobby, Robby, etc.), secondary sort them by ascending ID.

Input Format

The STUDENTS table is described as follows:
| Column | Type|
| :---:  |  :---:|
| ID | Integer |
| Name | String |
| Marks | Integer|
The name column only contains uppercase (A-Z) and lowercase (a-z) letters.
Sample Input
| ID | Name | Marks |
| :--:|:--: | :--: |
| 1 | Ashley | 81 |
| 2 | Samantha | 75 |
| 3 | Julia | 76 |
| 4 | Belvet | 84 |

Sample Output : Ashley, Julia, Belvet
Explanation

Only Ashley, Julia, and Belvet have Marks > . If you look at the last three characters of each of their names, there are no duplicates and 'ley' < 'lia' < 'vet'.
    
    Solution 1: SELECT NAME FROM STUDENTS WHERE MARKS > 75 ORDER BY SUBSTR(NAME, -3) , ID ;
    
### Employee Names
Q18.Write a query that prints a list of employee names (i.e.: the name attribute) from the Employee table in alphabetical order.

Input Format

The Employee table containing employee data for a company is described as follows:    
| Column | Type|
| :---:  |  :---:|
| employee_id | Integer |
| name | String |
| months | Integer|
| salary | Integer|

where employee_id is an employee's ID number, name is their name, months is the total number of months they've been working for the company, and salary is their monthly salary.

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
Q19Write a query that prints a list of employee names (i.e.: the name attribute) for employees in Employee having a salary greater than $ 2000 per month who have been employees for less than 10 months. Sort your result by ascending employee_id.

Input Format

The Employee table containing employee data for a company is described as follows:

| Column | Type|
| :---:  |  :---:|
| employee_id | Integer |
| name | String |
| months | Integer|
| salary | Integer|

where employee_id is an employee's ID number, name is their name, months is the total number of months they've been working for the company, and salary is their monthly salary.
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
Explanation

Angela has been an employee for 1 month and earns $3443 per month.
Michael has been an employee for 6 months and earns $2017 per month.
Todd has been an employee for 5 months and earns $3396 per month.
Joe has been an employee for 9 months and earns $3573 per month.
We order our output by ascending employee_id.

    Solution : SELECT NAME FROM EMPLOYEE WHERE SALARY > 2000 AND MONTHS < 10 ORDER BY EMPLOYEE_ID ASC;
