### City
## Aggregation - COUNT, MIN, MAX, AVG, SUM

The CITY table is described as follows:
| FIELD | TYPE |
| :---: | :---: |
| ID | NUMBER |
| NAME | VARCHAR(20) |
| COUNTRYCODE | VARCHAR(20) |
| DISTRICT | VARCHAR(20) |
|POPULATION | NUMBER |

### Average Population
 Q1.Query the average population for all cities in CITY, rounded down to the nearest integer.
 
    Solution : select round(avg(population)) from city;
### Japan Population
 Q2.Query the sum of the populations for all Japanese cities in CITY. The COUNTRYCODE for Japan is JPN.
  
    Solution :SELECT SUM(POPULATION) FROM CITY WHERE COUNTRYCODE ='JPN';
### Population Density Difference
Q3. Query the difference between the maximum and minimum populations in CITY.
  
    Solution :SELECT MAX(POPULATION) - MIN(POPULATION) FROM CITY;

### Revising Aggregations - The Count Function
 Q6.Query a count of the number of cities in CITY having a Population larger than 100000.
 
    Solution : SELECT COUNT(POPULATION) FROM CITY WHERE POPULATION > 100000;
### Revising Aggregations - The Sum Function
 Q7.Query the total population of all cities in CITY where District is California.
 
    Solution : SELECT SUM(POPULATION) FROM CITY WHERE DISTRICT = 'California';
### Revising Aggregations - Averages
 Q8. Query the average population of all cities in CITY where District is California.
 
    Solution : SELECT AVG(POPULATION) FROM CITY WHERE DISTRICT ='California';
