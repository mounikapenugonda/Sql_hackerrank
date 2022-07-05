## Weather Observation Station 20
A median is defined as a number separating the higher half of a data set from the lower half. Query the median of the Northern Latitudes (LAT_N) from STATION
and round your answer to 4 decimal places.

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

    Solution :  SET @R = 0;

                SELECT ROUND(AVG(LAT_N),4)
                FROM (SELECT (@R := @R + 1) AS MEDIAN ,LAT_N FROM STATION ORDER BY LAT_N ) AS T 
                WHERE 
                MEDIAN = (SELECT CEIL(COUNT(*)/2) FROM STATION) OR
                MEDIAN = (SELECT FLOOR((COUNT(*)/2)+1)FROM STATION);
