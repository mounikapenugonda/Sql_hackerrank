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
    
