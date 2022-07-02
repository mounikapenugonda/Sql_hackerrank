### Revising the Select Query 

The CITY table is described as follows:
| FIELD | TYPE |
| :---: | :---: |
| ID | NUMBER |
| NAME | VARCHAR(20) |
| COUNTRYCODE | VARCHAR(20) |
| DISTRICT | VARCHAR(20) |
|POPULATION | NUMBER |


### Revising the Select Query - |
Q1: Query all columns for all American cities in the CITY table with populations larger than 100000. The CountryCode for America is USA.

    Solution : SELECT * FROM CITY WHERE POPULATION > 100000 AND COUNTRYCODE = "USA";    
### Revising the Select Query - ||
Q2.Query the NAME field for all American cities in the CITY table with populations larger than 120000. The CountryCode for America is USA.

    Solution : SELECT NAME FROM CITY WHERE POPULATION > 120000 AND COUNTRYCODE = "USA";
### Select All
Q3. Query all columns (attributes) for every row in the CITY table.

   Solution : SELECT * FROM CITY;    
### Select by ID
 Q4. Query all columns for a city in CITY with the ID 1661.
 
     Solution : SELECT * FROM CITY WHERE ID = 1661;
 ### Average Population
 Q5.Query the average population for all cities in CITY, rounded down to the nearest integer.
 
    Solution : select round(avg(population)) from city;
 
  
