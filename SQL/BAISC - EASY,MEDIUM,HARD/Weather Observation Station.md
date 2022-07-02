### WEATHER OBSERVATION STATION  DATA

The STATION table is described as follows:
| FIELD | TYPE |
| :---: | :---: |
| ID | NUMBER |
| CITY | VARCHAR(20) |
| STATE | VARCHAR(20) |
| LAT_N | NUMBER |
| LONG_W | NUMBER |
where LAT_N is the northern latitude and LONG_W is the western longitude.

### WEATHER OBSERVATION STATION 1
Q1. Query a list of CITY and STATE from the STATION table.

    Solution : SELECT CITY, STATE FROM STATION;
### WEATHER OBSERVATION STATION 3   
Q2. Query a list of CITY names from STATION for cities that have an even ID number. Print the results in any order, but exclude duplicates from the answer.
 
    Solution : SELECT DISTINCT CITY FROM STATION WHERE ID % 2 =0 ORDER BY CITY ASC;     
### WEATHER OBSERVATION STATION 4
Q3.Find the difference between the total number of CITY entries in the table and the number of distinct CITY entries in the table.
For example, if there are three records in the table with CITY values 'New York', 'New York', 'Bengalaru', there are 2 different city names: 'New York' and 'Bengalaru'. The query returns , because total number of records - number of unique city names = 3-2 =1

    Solution : SELECT COUNT(CITY) - COUNT(DISTINCT(CITY)) FROM STATION;
### WEATHER OBSERVATION STATION 6
Q4. Query the list of CITY names starting with vowels (i.e., a, e, i, o, or u) from STATION. Your result cannot contain duplicates.

    Solution 1:Solution 1:SELECT DISTINCT(CITY) FROM STATION WHERE CITY LIKE 'A%' OR CITY LIKE 'E%' OR CITY LIKE 'I%' OR CITY LIKE 'O%' OR CITY LIKE 'U%';
    Solution 2:SELECT DISTINCT CITY FROM STATION WHERE CITY LIKE 'A%' OR CITY LIKE 'E%' OR CITY LIKE 'I%' OR CITY LIKE 'O%' OR CITY LIKE 'U%'
    Solution 3: SELECT DISTINCT(CITY) FROM STATION WHERE CITY LIKE 'A%' OR CITY LIKE 'E%' OR CITY LIKE 'I%' OR CITY LIKE 'O%' OR CITY LIKE 'U%' ORDER BY CITY ASC;
### WEATHER OBSERVATION STATION 7
Q5.Query the list of CITY names ending with vowels (a, e, i, o, u) from STATION. Your result cannot contain duplicates. 

    Solution 1 : SELECT DISTINCT CITY FROM STATION WHERE CITY LIKE '%A' OR CITY LIKE '%E' OR CITY LIKE '%I' OR CITY LIKE '%O' OR CITY LIKE '%U';
    Solution 2 : SELECT DISTINCT CITY FROM STATION WHERE CITY LIKE '%A' OR CITY LIKE '%E' OR CITY LIKE '%I' OR CITY LIKE '%O' OR CITY LIKE '%U' ORDER BY CITY ASC;
    Solution 3 : SELECT DISTINCT CITY FROM STATION WHERE CITY LIKE '%A' OR CITY LIKE '%E' OR CITY LIKE '%I' OR CITY LIKE '%O' OR CITY LIKE '%U' ORDER BY CITY DESC;
### WEATHER OBSERVATION STATION 8
Q6.Query the list of CITY names from STATION which have vowels (i.e., a, e, i, o, and u) as both their first and last characters. Your result cannot contain duplicates.

    Solution : SELECT DISTINCT CITY FROM STATION WHERE (CITY LIKE 'A%' OR CITY LIKE 'E%' OR CITY LIKE 'I%' OR CITY LIKE 'O%' OR CITY LIKE 'U%' ) AND (CITY LIKE '%A' OR CITY LIKE '%E' OR CITY LIKE '%I' OR CITY LIKE '%O' OR CITY LIKE '%U' );
### WEATHER OBSERVATION STATION 9
Q7.Query the list of CITY names from STATION that do not start with vowels. Your result cannot contain duplicates.

    Solution : SELECT DISTINCT CITY FROM STATION WHERE CITY NOT LIKE 'A%' AND CITY NOT LIKE 'E%' AND CITY NOT LIKE 'I%' AND CITY NOT LIKE 'O%' AND CITY NOT LIKE 'U%' ;
### WEATHER OBSERVATION STATION 10
Q8.Query the list of CITY names from STATION that do not end with vowels. Your result cannot contain duplicates.

    Solution :SELECT DISTINCT CITY FROM STATION WHERE CITY NOT LIKE '%A' AND CITY NOT LIKE '%E' AND CITY NOT LIKE '%I' AND CITY NOT LIKE '%O' AND CITY NOT LIKE '%U' ;
    
### WEATHER OBSERVATION STATION 11
Q9.Query the list of CITY names from STATION that either do not start with vowels or do not end with vowels. Your result cannot contain duplicates.

    Solution :SELECT DISTINCT CITY FROM STATION WHERE (CITY NOT LIKE 'A%' AND CITY NOT LIKE 'E%' AND CITY NOT LIKE 'I%' AND CITY NOT LIKE 'O%' AND CITY NOT LIKE 'U%' ) OR (CITY NOT LIKE '%A' AND CITY NOT LIKE '%E' AND CITY NOT LIKE '%I' AND CITY NOT LIKE '%O' AND CITY NOT LIKE '%U' );

### WEATHER OBSERVATION STATION 12
Q10.Query the list of CITY names from STATION that do not start with vowels and do not end with vowels. Your result cannot contain duplicates.

    Solution :SELECT DISTINCT CITY FROM STATION WHERE (CITY NOT LIKE 'A%' AND CITY NOT LIKE 'E%' AND CITY NOT LIKE 'I%' AND CITY NOT LIKE 'O%' AND CITY NOT LIKE 'U%' ) AND (CITY NOT LIKE '%A' AND CITY NOT LIKE '%E' AND CITY NOT LIKE '%I' AND CITY NOT LIKE '%O' AND CITY NOT LIKE '%U' );


  
  
  
 

    
