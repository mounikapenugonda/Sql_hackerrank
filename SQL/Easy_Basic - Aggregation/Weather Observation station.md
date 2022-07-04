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

### WEATHER OBSERVATION STATION 2
Q2. Query the following two values from the STATION table:
The sum of all values in LAT_N rounded to a scale of  decimal places.
The sum of all values in LONG_W rounded to a scale of  decimal places.
Output Format :: 
Your results must be in the form: lat lon
where lat is the sum of all values in LAT_N and lon is the sum of all values in LONG_W. Both results must be rounded to a scale of 2 decimal places.

    Solution : SELECT ROUND(SUM(LAT_N),2) , ROUND(SUM(LONG_W),2) FROM STATION;
    Output : 42850.04 47381.48
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
