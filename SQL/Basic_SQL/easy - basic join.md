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
    Solution 2: select sum(city.population) from CITY inner join COUNTRY on city.CountryCode = COUNTRY.Code where country.continent = 'asia';
both are same just inner join changed
    output :: 27028484
### African Cities
Q3. Given the CITY and COUNTRY tables, query the names of all cities where the CONTINENT is 'Africa'.

Note: CITY.CountryCode and COUNTRY.Code are matching key columns.
use the above tables for city and country

    Solution : select city.name from country inner join city on city.CountryCode = COUNTRY.Code where country.continent = 'africa';
### Average Population of Each Continent
Q4. Given the CITY and COUNTRY tables, query the names of all the continents (COUNTRY.Continent) and their respective average city populations (CITY.Population) rounded down to the nearest integer.

Note: CITY.CountryCode and COUNTRY.Code are matching key columns. \N
use the above tables for city and country

    Solution : SELECT COUNTRY.CONTINENT, FLOOR(AVG(CITY.POPULATION)) FROM COUNTRY, CITY WHERE  CITY.CountryCode = COUNTRY.Code GROUP BY COUNTRY.CONTINENT;
    floor : function rounds the number, towards zero, always down.
