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
    
### WEATHER OBSERVATION STATION 1
Q7. Query a list of CITY and STATE from the STATION table.
The STATION table is described as follows:
| FIELD | TYPE |
| :---: | :---: |
| ID | NUMBER |
| CITY | VARCHAR(20) |
| STATE | VARCHAR(20) |
| LAT_N | NUMBER |
| LONG_W | NUMBER |
where LAT_N is the northern latitude and LONG_W is the western longitude.

    Solution : SELECT CITY, STATE FROM STATION;
    
### WEATHER OBSERVATION STATION 3
Q8. Query a list of CITY names from STATION for cities that have an even ID number. Print the results in any order, but exclude duplicates from the answer.
The STATION table is described as follows:
| FIELD | TYPE |
| :---: | :---: |
| ID | NUMBER |
| CITY | VARCHAR(20) |
| STATE | VARCHAR(20) |
| LAT_N | NUMBER |
| LONG_W | NUMBER |
where LAT_N is the northern latitude and LONG_W is the western longitude.

    Solution : SELECT DISTINCT CITY FROM STATION WHERE ID % 2 =0 ORDER BY CITY ASC;

### WEATHER OBSERVATION STATION 4
Q9.Find the difference between the total number of CITY entries in the table and the number of distinct CITY entries in the table.
The STATION table is described as follows:
| FIELD | TYPE |
| :---: | :---: |
| ID | NUMBER |
| CITY | VARCHAR(20) |
| STATE | VARCHAR(20) |
| LAT_N | NUMBER |
| LONG_W | NUMBER |

where LAT_N is the northern latitude and LONG_W is the western longitude.
For example, if there are three records in the table with CITY values 'New York', 'New York', 'Bengalaru', there are 2 different city names: 'New York' and 'Bengalaru'. The query returns , because total number of records - number of unique city names = 3-2 =1

    Solution : SELECT COUNT(CITY) - COUNT(DISTINCT(CITY)) FROM STATION;

### WEATHER OBSERVATION STATION 6
Q10. Query the list of CITY names starting with vowels (i.e., a, e, i, o, or u) from STATION. Your result cannot contain duplicates.

Input Format

The STATION table is described as follows:
| FIELD | TYPE |
| :---: | :---: |
| ID | NUMBER |
| CITY | VARCHAR(20) |
| STATE | VARCHAR(20) |
| LAT_N | NUMBER |
| LONG_W | NUMBER |

where LAT_N is the northern latitude and LONG_W is the western longitude.

    Solution 1:Solution 1:SELECT DISTINCT(CITY) FROM STATION WHERE CITY LIKE 'A%' OR CITY LIKE 'E%' OR CITY LIKE 'I%' OR CITY LIKE 'O%' OR CITY LIKE 'U%';
    Solution 2:SELECT DISTINCT CITY FROM STATION WHERE CITY LIKE 'A%' OR CITY LIKE 'E%' OR CITY LIKE 'I%' OR CITY LIKE 'O%' OR CITY LIKE 'U%'
    Solution 3: SELECT DISTINCT(CITY) FROM STATION WHERE CITY LIKE 'A%' OR CITY LIKE 'E%' OR CITY LIKE 'I%' OR CITY LIKE 'O%' OR CITY LIKE 'U%' ORDER BY CITY ASC;
    
### WEATHER OBSERVATION STATION 7
Q11.Query the list of CITY names ending with vowels (a, e, i, o, u) from STATION. Your result cannot contain duplicates.

Input Format

The STATION table is described as follows:
| FIELD | TYPE |
| :---: | :---: |
| ID | NUMBER |
| CITY | VARCHAR(20) |
| STATE | VARCHAR(20) |
| LAT_N | NUMBER |
| LONG_W | NUMBER |

where LAT_N is the northern latitude and LONG_W is the western longitude.

    Solution 1 : SELECT DISTINCT CITY FROM STATION WHERE CITY LIKE '%A' OR CITY LIKE '%E' OR CITY LIKE '%I' OR CITY LIKE '%O' OR CITY LIKE '%U';
    Solution 2 : SELECT DISTINCT CITY FROM STATION WHERE CITY LIKE '%A' OR CITY LIKE '%E' OR CITY LIKE '%I' OR CITY LIKE '%O' OR CITY LIKE '%U' ORDER BY CITY ASC;
    Solution 3 : SELECT DISTINCT CITY FROM STATION WHERE CITY LIKE '%A' OR CITY LIKE '%E' OR CITY LIKE '%I' OR CITY LIKE '%O' OR CITY LIKE '%U' ORDER BY CITY DESC;
    
### WEATHER OBSERVATION STATION 8
Q12.Query the list of CITY names from STATION which have vowels (i.e., a, e, i, o, and u) as both their first and last characters. Your result cannot contain duplicates.

Input Format

The STATION table is described as follows:
| FIELD | TYPE |
| :---: | :---: |
| ID | NUMBER |
| CITY | VARCHAR(20) |
| STATE | VARCHAR(20) |
| LAT_N | NUMBER |
| LONG_W | NUMBER |

where LAT_N is the northern latitude and LONG_W is the western longitude.

    Solution : SELECT DISTINCT CITY FROM STATION WHERE (CITY LIKE 'A%' OR CITY LIKE 'E%' OR CITY LIKE 'I%' OR CITY LIKE 'O%' OR CITY LIKE 'U%' ) AND (CITY LIKE '%A' OR CITY LIKE '%E' OR CITY LIKE '%I' OR CITY LIKE '%O' OR CITY LIKE '%U' );
    
### WEATHER OBSERVATION STATION 9
Q13.Query the list of CITY names from STATION that do not start with vowels. Your result cannot contain duplicates.

Input Format

The STATION table is described as follows:
| FIELD | TYPE |
| :---: | :---: |
| ID | NUMBER |
| CITY | VARCHAR(20) |
| STATE | VARCHAR(20) |
| LAT_N | NUMBER |
| LONG_W | NUMBER |

where LAT_N is the northern latitude and LONG_W is the western longitude.

    Solution : SELECT DISTINCT CITY FROM STATION WHERE CITY NOT LIKE 'A%' AND CITY NOT LIKE 'E%' AND CITY NOT LIKE 'I%' AND CITY NOT LIKE 'O%' AND CITY NOT LIKE 'U%' ;

### WEATHER OBSERVATION STATION 10
Q14.Query the list of CITY names from STATION that do not end with vowels. Your result cannot contain duplicates.

Input Format

The STATION table is described as follows:
| FIELD | TYPE |
| :---: | :---: |
| ID | NUMBER |
| CITY | VARCHAR(20) |
| STATE | VARCHAR(20) |
| LAT_N | NUMBER |
| LONG_W | NUMBER |

where LAT_N is the northern latitude and LONG_W is the western longitude.

    Solution :SELECT DISTINCT CITY FROM STATION WHERE CITY NOT LIKE '%A' AND CITY NOT LIKE '%E' AND CITY NOT LIKE '%I' AND CITY NOT LIKE '%O' AND CITY NOT LIKE '%U' ;
    
### WEATHER OBSERVATION STATION 11
Q15.Query the list of CITY names from STATION that either do not start with vowels or do not end with vowels. Your result cannot contain duplicates.

Input Format

The STATION table is described as follows:
| FIELD | TYPE |
| :---: | :---: |
| ID | NUMBER |
| CITY | VARCHAR(20) |
| STATE | VARCHAR(20) |
| LAT_N | NUMBER |
| LONG_W | NUMBER |

where LAT_N is the northern latitude and LONG_W is the western longitude.
    Solution :SELECT DISTINCT CITY FROM STATION WHERE (CITY NOT LIKE 'A%' AND CITY NOT LIKE 'E%' AND CITY NOT LIKE 'I%' AND CITY NOT LIKE 'O%' AND CITY NOT LIKE 'U%' ) OR (CITY NOT LIKE '%A' AND CITY NOT LIKE '%E' AND CITY NOT LIKE '%I' AND CITY NOT LIKE '%O' AND CITY NOT LIKE '%U' );

### WEATHER OBSERVATION STATION 12
Q16.Query the list of CITY names from STATION that do not start with vowels and do not end with vowels. Your result cannot contain duplicates.

Input Format

The STATION table is described as follows:
| FIELD | TYPE |
| :---: | :---: |
| ID | NUMBER |
| CITY | VARCHAR(20) |
| STATE | VARCHAR(20) |
| LAT_N | NUMBER |
| LONG_W | NUMBER |

where LAT_N is the northern latitude and LONG_W is the western longitude.
    Solution :SELECT DISTINCT CITY FROM STATION WHERE (CITY NOT LIKE 'A%' AND CITY NOT LIKE 'E%' AND CITY NOT LIKE 'I%' AND CITY NOT LIKE 'O%' AND CITY NOT LIKE 'U%' ) AND (CITY NOT LIKE '%A' AND CITY NOT LIKE '%E' AND CITY NOT LIKE '%I' AND CITY NOT LIKE '%O' AND CITY NOT LIKE '%U' );

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
    
  


