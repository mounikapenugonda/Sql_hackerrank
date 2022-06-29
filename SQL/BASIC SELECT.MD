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

