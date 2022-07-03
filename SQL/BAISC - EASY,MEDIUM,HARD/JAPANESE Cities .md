### JAPANESE Cities 

The CITY table is described as follows:
| FIELD | TYPE |
| :---: | :---: |
| ID | NUMBER |
| NAME | VARCHAR(20) |
| COUNTRYCODE | VARCHAR(20) |
| DISTRICT | VARCHAR(20) |
|POPULATION | NUMBER |

### JAPANESE Cities Attributes
Q1. Query all attributes of every Japanese city in the CITY table. The COUNTRYCODE for Japan is JPN.

    Solution : SELECT * FROM CITY WHERE COUNTRYCODE = "JPN";
### JAPANESE Cities NAMES
Q2. Query the names of all the Japanese cities in the CITY table. The COUNTRYCODE for Japan is JPN.

    Solution : SELECT NAME FROM CITY WHERE COUNTRYCODE = "JPN";
    
### Population Census
Q3. Given the CITY and COUNTRY tables, query the sum of the populations of all cities where the CONTINENT is 'Asia'.

Note: CITY.CountryCode and COUNTRY.Code are matching key columns.
Input Format

The CITY and COUNTRY tables are described as follows:
| FIELD | TYPE |
| :---: | :---: |
| ID | NUMBER |
| NAME | VARCHAR(20) |
| COUNTRYCODE | VARCHAR(20) |
| DISTRICT | VARCHAR(20) |
|POPULATION | NUMBER |

| FIELD | TYPE |
| :---: | :---: |
| CODE | VARCHAR(33) |
| NAME | VARCHAR(20) |
| CONTINENT | VARCHAR(20) |
| REGION | VARCHAR(20) |
| SURFACEAREA | NUMBER |
| INDEPYEAR | VARCHAR(20) |
|POPULATION | NUMBER |
| LIFEEXPECTANCY | VARCHAR(20) |
|GNP | NUMBER |
| GNPOLD | VARCHAR(20) |
| LOCALNAME | VARCHAR(20) |
| GOVERNMENTFORM | VARCHAR(20) |
| HEADOFSTATE | VARCHAR(20) |
| CAPITAL | VARCHAR(20) |
| CODE2 | VARCHAR(20) |

    Solution 1: select sum(city.population) from country inner join city on city.CountryCode = COUNTRY.Code where country.continent = 'asia'; 
    sOLUTION 2: select sum(city.population) from CITY inner join COUNTRY on city.CountryCode = COUNTRY.Code where country.continent = 'asia';
    both are same just inner join changed
    
