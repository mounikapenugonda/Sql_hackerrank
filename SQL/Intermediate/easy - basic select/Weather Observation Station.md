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
