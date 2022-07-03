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
### WEATHER OBSERVATION STATION 2
Q2. Query the following two values from the STATION table:
The sum of all values in LAT_N rounded to a scale of  decimal places.
The sum of all values in LONG_W rounded to a scale of  decimal places.
Output Format :: 
Your results must be in the form: lat lon
where lat is the sum of all values in LAT_N and lon is the sum of all values in LONG_W. Both results must be rounded to a scale of 2 decimal places.

    Solution : SELECT ROUND(SUM(LAT_N),2) , ROUND(SUM(LONG_W),2) FROM STATION;
    Output : 42850.04 47381.48
### WEATHER OBSERVATION STATION 3   
Q3. Query a list of CITY names from STATION for cities that have an even ID number. Print the results in any order, but exclude duplicates from the answer.
 
    Solution : SELECT DISTINCT CITY FROM STATION WHERE ID % 2 =0 ORDER BY CITY ASC;     
### WEATHER OBSERVATION STATION 4
Q4.Find the difference between the total number of CITY entries in the table and the number of distinct CITY entries in the table.
For example, if there are three records in the table with CITY values 'New York', 'New York', 'Bengalaru', there are 2 different city names: 'New York' and 'Bengalaru'. The query returns , because total number of records - number of unique city names = 3-2 =1

    Solution : SELECT COUNT(CITY) - COUNT(DISTINCT(CITY)) FROM STATION;
### WEATHER OBSERVATION STATION 5
Q5.Query the two cities in STATION with the shortest and longest CITY names, as well as their respective lengths (i.e.: number of characters in the name). If there is more than one smallest or largest city, choose the one that comes first when ordered alphabetically.
Sample Input ::
For example, CITY has four entries: DEF, ABC, PQRS and WXY.

Sample Output :: 
ABC 3
PQRS 4
Explanation :: When ordered alphabetically, the CITY names are listed as ABC, DEF, PQRS, and WXY, with lengths  and . The longest name is PQRS, but there are  options for shortest named city. Choose ABC, because it comes first alphabetically.

Note :: You can write two separate queries to get the desired output. It need not be a single query.

    Solution : (select city, length(city) from station order by length(city), city limit 1) union (select city, length(city) from station order by length(city) desc, city limit 1);
    explanation: 1st query will order city by length and we are mentioning limit 1 means it will give 1st row and it will give city , lentgh of that city same goes to 2nd query, lastly we will combine these statements.
    
### WEATHER OBSERVATION STATION 6
Q6. Query the list of CITY names starting with vowels (i.e., a, e, i, o, or u) from STATION. Your result cannot contain duplicates.

    Solution 1:Solution 1:SELECT DISTINCT(CITY) FROM STATION WHERE CITY LIKE 'A%' OR CITY LIKE 'E%' OR CITY LIKE 'I%' OR CITY LIKE 'O%' OR CITY LIKE 'U%';
    Solution 2:SELECT DISTINCT CITY FROM STATION WHERE CITY LIKE 'A%' OR CITY LIKE 'E%' OR CITY LIKE 'I%' OR CITY LIKE 'O%' OR CITY LIKE 'U%'
    Solution 3: SELECT DISTINCT(CITY) FROM STATION WHERE CITY LIKE 'A%' OR CITY LIKE 'E%' OR CITY LIKE 'I%' OR CITY LIKE 'O%' OR CITY LIKE 'U%' ORDER BY CITY ASC;
### WEATHER OBSERVATION STATION 7
Q7.Query the list of CITY names ending with vowels (a, e, i, o, u) from STATION. Your result cannot contain duplicates. 

    Solution 1 : SELECT DISTINCT CITY FROM STATION WHERE CITY LIKE '%A' OR CITY LIKE '%E' OR CITY LIKE '%I' OR CITY LIKE '%O' OR CITY LIKE '%U';
    Solution 2 : SELECT DISTINCT CITY FROM STATION WHERE CITY LIKE '%A' OR CITY LIKE '%E' OR CITY LIKE '%I' OR CITY LIKE '%O' OR CITY LIKE '%U' ORDER BY CITY ASC;
    Solution 3 : SELECT DISTINCT CITY FROM STATION WHERE CITY LIKE '%A' OR CITY LIKE '%E' OR CITY LIKE '%I' OR CITY LIKE '%O' OR CITY LIKE '%U' ORDER BY CITY DESC;
### WEATHER OBSERVATION STATION 8
Q8.Query the list of CITY names from STATION which have vowels (i.e., a, e, i, o, and u) as both their first and last characters. Your result cannot contain duplicates.

    Solution : SELECT DISTINCT CITY FROM STATION WHERE (CITY LIKE 'A%' OR CITY LIKE 'E%' OR CITY LIKE 'I%' OR CITY LIKE 'O%' OR CITY LIKE 'U%' ) AND (CITY LIKE '%A' OR CITY LIKE '%E' OR CITY LIKE '%I' OR CITY LIKE '%O' OR CITY LIKE '%U' );
### WEATHER OBSERVATION STATION 9
Q9.Query the list of CITY names from STATION that do not start with vowels. Your result cannot contain duplicates.

    Solution : SELECT DISTINCT CITY FROM STATION WHERE CITY NOT LIKE 'A%' AND CITY NOT LIKE 'E%' AND CITY NOT LIKE 'I%' AND CITY NOT LIKE 'O%' AND CITY NOT LIKE 'U%' ;
### WEATHER OBSERVATION STATION 10
Q10.Query the list of CITY names from STATION that do not end with vowels. Your result cannot contain duplicates.

    Solution :SELECT DISTINCT CITY FROM STATION WHERE CITY NOT LIKE '%A' AND CITY NOT LIKE '%E' AND CITY NOT LIKE '%I' AND CITY NOT LIKE '%O' AND CITY NOT LIKE '%U' ;
    
### WEATHER OBSERVATION STATION 11
Q11.Query the list of CITY names from STATION that either do not start with vowels or do not end with vowels. Your result cannot contain duplicates.

    Solution :SELECT DISTINCT CITY FROM STATION WHERE (CITY NOT LIKE 'A%' AND CITY NOT LIKE 'E%' AND CITY NOT LIKE 'I%' AND CITY NOT LIKE 'O%' AND CITY NOT LIKE 'U%' ) OR (CITY NOT LIKE '%A' AND CITY NOT LIKE '%E' AND CITY NOT LIKE '%I' AND CITY NOT LIKE '%O' AND CITY NOT LIKE '%U' );

### WEATHER OBSERVATION STATION 12
Q12.Query the list of CITY names from STATION that do not start with vowels and do not end with vowels. Your result cannot contain duplicates.

    Solution :SELECT DISTINCT CITY FROM STATION WHERE (CITY NOT LIKE 'A%' AND CITY NOT LIKE 'E%' AND CITY NOT LIKE 'I%' AND CITY NOT LIKE 'O%' AND CITY NOT LIKE 'U%' ) AND (CITY NOT LIKE '%A' AND CITY NOT LIKE '%E' AND CITY NOT LIKE '%I' AND CITY NOT LIKE '%O' AND CITY NOT LIKE '%U' );
### WEATHER OBSERVATION STATION 13
Q13.Query the sum of Northern Latitudes (LAT_N) from STATION having values greater than 38.7880 and less than 137.2345 . Truncate your answer to  decimal places.

    Solution : SELECT ROUND(SUM(LAT_N),4) FROM STATION WHERE LAT_N <137.2345 AND LAT_N > 38.7880;
    output : 36354.8135
### WEATHER OBSERVATION STATION 14
Q14.Query the greatest value of the Northern Latitudes (LAT_N) from STATION that is less than 137.2345. Truncate your answer to 4 decimal places.

    Solution : SELECT ROUND(MAX(LAT_N),4) FROM STATION WHERE LAT_N < 137.2345;
    output : 137.0193  
### WEATHER OBSERVATION STATION 15
Q15. Query the Western Longitude (LONG_W) for the largest Northern Latitude (LAT_N) in STATION that is less than 137.2345. Round your answer to 4 decimal places.

    Solution :SELECT ROUND(LONG_W,4) FROM STATION WHERE LAT_N = (SELECT MAX(LAT_N) FROM STATION WHERE LAT_N< 137.2345);
    output : 117.2465
### WEATHER OBSERVATION STATION 16
Q16. Query the smallest Northern Latitude (LAT_N) from STATION that is greater than 38.7780. Round your answer to 4 decimal places.

    Solution :SELECT ROUND(MIN(LAT_N),4) FROM STATION WHERE LAT_N > 38.7780;
    output : 38.8526
### WEATHER OBSERVATION STATION 17
Q17. Query the Western Longitude (LONG_W)where the smallest Northern Latitude (LAT_N) in STATION is greater than 38.7780. Round your answer to 4 decimal places.  

    Solution :SELECT ROUND(LONG_W,4) FROM STATION WHERE LAT_N = (SELECT MIN(LAT_N) FROM STATION WHERE LAT_N> 38.7780);
    output : 70.1378
### WEATHER OBSERVATION STATION 18
Q18. Consider P(a,b)  and P2(c,d) to be two points on a 2D plane.

a happens to equal the minimum value in Northern Latitude (LAT_N in STATION).
b happens to equal the minimum value in Western Longitude (LONG_W in STATION).
c happens to equal the maximum value in Northern Latitude (LAT_N in STATION).
d happens to equal the maximum value in Western Longitude (LONG_W in STATION).
Query the Manhattan Distance between points  and  and round it to a scale of  decimal places.
Manhattan Distance :::: The distance between two points measured along axes at right angles. In a plane with p1 at (x1, y1) and p2 at (x2, y2), it is |x1 - x2| + |y1 - y2|.

    Solution :SELECT ROUND(ABS(MAX(LAT_N) - MIN(LAT_N)) + ABS(MAX(LONG_W)- MIN(LONG_W)),4) FROM STATION;
    Output : 259.6859

    
