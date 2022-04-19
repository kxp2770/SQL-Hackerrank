**[Revising the Select Query-1](https://www.hackerrank.com/challenges/revising-the-select-query)**


Query all columns for all American cities in CITY with populations larger than 100,000. The CountryCode for America is USA.

Input Format

The CITY table is described as follows:

|  Field | Type |
|------|------|
| ID  | NUMBER |
| NAME | VARCHAR2(17) |
| COUNTRY CODE  | VARCHAR2(3) |
| DISTRICT |  VARCHAR2(20) |
| POPULATION | NUMBER |

**Solution**
```sql
SELECT * 
FROM CITY
WHERE COUNTRYCODE = 'USA' AND POPULATION > 100000;
```


**[Revising the Select Query-2](https://www.hackerrank.com/challenges/revising-the-select-query-2)**

Query the names of all American cities in CITY with populations larger than 120,000. The CountryCode for America is USA.

Input Format

The CITY table is described as follows:

|  Field | Type |
|------|------|
| ID  | NUMBER |
| NAME | VARCHAR2(17) |
| COUNTRY CODE  | VARCHAR2(3) |
| DISTRICT |  VARCHAR2(20) |
| POPULATION | NUMBER |


**Solution**
```sql
SELECT NAME 
FROM CITY 
WHERE COUNTRYCODE = 'USA' AND POPULATION > 120000;
```


**[Select All](https://www.hackerrank.com/challenges/select-all-sql)**

Query all columns for every row in the CITY table.

Input Format

The CITY table is described as follows:

|  Field | Type |
|------|------|
| ID  | NUMBER |
| NAME | VARCHAR2(17) |
| COUNTRY CODE  | VARCHAR2(3) |
| DISTRICT |  VARCHAR2(20) |
| POPULATION | NUMBER |


**Solution**
```sql
SELECT * 
FROM CITY;
```


**[Select by ID](https://www.hackerrank.com/challenges/select-by-id)**

Query all columns for a city in CITY with the ID 1661.

Input Format

The CITY table is described as follows:

|  Field | Type |
|------|------|
| ID  | NUMBER |
| NAME | VARCHAR2(17) |
| COUNTRY CODE  | VARCHAR2(3) |
| DISTRICT |  VARCHAR2(20) |
| POPULATION | NUMBER |


**Solution**
```sql
SELECT * 
FROM CITY 
WHERE ID = 1661; 
```


**[Japanese Cities' Detail](https://www.hackerrank.com/challenges/japanese-cities-detail)**

Query the details for all the Japanese cities in CITY. The COUNTRYCODE for Japan is JPN.

Input Format

The CITY table is described as follows:

|  Field | Type |
|------|------|
| ID  | NUMBER |
| NAME | VARCHAR2(17) |
| COUNTRY CODE  | VARCHAR2(3) |
| DISTRICT |  VARCHAR2(20) |
| POPULATION | NUMBER |


**Solution**
```sql
SELECT * 
FROM CITY 
WHERE COUNTRYCODE = 'JPN';        
```


**[Japanese Cities' Name](https://www.hackerrank.com/challenges/japanese-cities-name)**

Query the the names of all the Japanese cities in CITY. The COUNTRYCODE for Japan is JPN.

Input Format

The CITY table is described as follows:

|  Field | Type |
|------|------|
| ID  | NUMBER |
| NAME | VARCHAR2(17) |
| COUNTRY CODE  | VARCHAR2(3) |
| DISTRICT |  VARCHAR2(20) |
| POPULATION | NUMBER |


**Solution**
```sql
SELECT NAME
FROM CITY
WHERE COUNTRYCODE = 'JPN';        
```


**[Weather Observation Station 1](https://www.hackerrank.com/challenges/weather-observation-station-1)**

Query a list of CITY and STATE from STATION.

Input Format

The STATION table is described as follows:

|  Field | Type |
|------|------|
| ID  | NUMBER |
| CITY | VARCHAR2(21) |
| STATE  | VARCHAR2(2) |
| LAT_N |  NUMBER |
| LONG_W | NUMBER |


**Solution**
```sql
SELECT CITY, STATE
FROM STATION;
```


**[Weather Observation Station 3](https://www.hackerrank.com/challenges/weather-observation-station-3)**

Query a list of CITY names from STATION with even ID numbers only. You may print the results in any order, but must exclude duplicates from your answer.

Input Format

The STATION table is described as follows:

|  Field | Type |
|------|------|
| ID  | NUMBER |
| CITY | VARCHAR2(21) |
| STATE  | VARCHAR2(2) |
| LAT_N |  NUMBER |
| LONG_W | NUMBER |

where LAT_N is the northern latitude and LONG_W is the western longitude.

**Solution**
```sql
SELECT DISTINCT CITY
FROM 
WHERE MOD(ID, 2) = 0;    
```
[comment]: <> (MOD returns remainder after a division operation)


**[Weather Observation Station 4](https://www.hackerrank.com/challenges/weather-observation-station-4)**

Let NUM be the number of CITY entries in STATION, and NUMunique be the number of unique cities. Query the value of NUM−NUMunique from STATION.

In other words, query the number of non-unique CITY names in STATION by subtracting the number of unique CITY entries in the table from the total number of CITY entries in the table.

Input Format

The STATION table is described as follows:

|  Field | Type |
|------|------|
| ID  | NUMBER |
| CITY | VARCHAR2(21) |
| STATE  | VARCHAR2(2) |
| LAT_N |  NUMBER |
| LONG_W | NUMBER |

where LAT_N is the northern latitude and LONG_W is the western longitude.

**Solution**
```sql
SELECT (COUNT(city) - COUNT(DISTINCT(city)))
FROM STATION;
```


**[Weather Observation Station 5](https://www.hackerrank.com/challenges/weather-observation-station-5)**

Query the two cities in STATION with the shortest and longest CITY names, as well as their respective lengths (i.e.: number of characters in the name). If there is more than one smallest or largest city, choose the one that comes first when ordered alphabetically.

Input Format

The STATION table is described as follows:

|  Field | Type |
|------|------|
| ID  | NUMBER |
| CITY | VARCHAR2(21) |
| STATE  | VARCHAR2(2) |
| LAT_N |  NUMBER |
| LONG_W | NUMBER |

where LAT_N is the northern latitude and LONG_W is the western longitude.

*Sample Input*

Let's say that CITY only has four entries: DEF, ABC, PQRS and WXY

*Sample Output*

ABC 3 

PQRS 4

*Explanation*

When ordered alphabetically, the CITY names are listed as ABC, DEF, PQRS, and WXY, with the respective lengths 3,3,4,3,3,4, and 33. The longest-named city is obviously PQRS, but there are 33 options for shortest-named city; we choose ABC, because it comes first alphabetically.

**Solution**
```sql
SELECT city, LENGTH(city)
FROM station
ORDER BY LENGTH(city), city
LIMIT 1;

SELECT city, LENGTH(city)
FROM station
ORDER BY LENGTH(city) DESC, city DESC
LIMIT 1;     
```


**[Weather Observation Station 6](https://www.hackerrank.com/challenges/weather-observation-station-6)**

Query the list of CITY names starting with vowels (a, e, i, o, u) from STATION. Your result cannot contain duplicates.

Input Format

The STATION table is described as follows:

|  Field | Type |
|------|------|
| ID  | NUMBER |
| CITY | VARCHAR2(21) |
| STATE  | VARCHAR2(2) |
| LAT_N |  NUMBER |
| LONG_W | NUMBER |

where LAT_N is the northern latitude and LONG_W is the western longitude.

**Solution**
```sql
SELECT DISTINCT CITY
FROM STATION
WHERE CITY LIKE 'a%' OR
      CITY LIKE 'e%' OR
      CITY LIKE 'i%' OR
      CITY LIKE 'o%' OR
      CITY LIKE 'u%';      
```


**[Weather Observation Station 7](https://www.hackerrank.com/challenges/weather-observation-station-7)**

Query the list of CITY names ending with vowels (a, e, i, o, u) from STATION. Your result cannot contain duplicates.

Input Format

The STATION table is described as follows:

|  Field | Type |
|------|------|
| ID  | NUMBER |
| CITY | VARCHAR2(21) |
| STATE  | VARCHAR2(2) |
| LAT_N |  NUMBER |
| LONG_W | NUMBER |

where LAT_N is the northern latitude and LONG_W is the western longitude.

**Solution**
```sql
SELECT DISTINCT CITY
FROM STATION
WHERE CITY LIKE '%a' OR
      CITY LIKE '%e' OR
      CITY LIKE '%i' OR
      CITY LIKE '%o' OR
      CITY LIKE '%u';       
```


**[Weather Observation Station 8](https://www.hackerrank.com/challenges/weather-observation-station-8/problem)**

Query the list of CITY names from STATION which have vowels (i.e., a, e, i, o, and u) as both their first and last characters. Your result cannot contain duplicates.

Input Format

The STATION table is described as follows:

|  Field | Type |
|------|------|
| ID  | NUMBER |
| CITY | VARCHAR2(21) |
| STATE  | VARCHAR2(2) |
| LAT_N |  NUMBER |
| LONG_W | NUMBER |

where LAT_N is the northern latitude and LONG_W is the western longitude.

**Solution**
```sql
SELECT DISTINCT CITY
FROM STATION
WHERE (CITY LIKE 'a%' OR
      CITY LIKE 'e%' OR
      CITY LIKE 'i%' OR
      CITY LIKE 'o%' OR
      CITY LIKE 'u%'
      )               AND (CITY LIKE '%a' OR
                           CITY LIKE '%e' OR
                           CITY LIKE '%i' OR
                           CITY LIKE '%o' OR
                           CITY LIKE '%u'    
                            );     
```


**[Weather Observation Station 9](https://www.hackerrank.com/challenges/weather-observation-station-9/problem)**

Query the list of CITY names from STATION that do not start with vowels. Your result cannot contain duplicates.

Input Format

The STATION table is described as follows:

|  Field | Type |
|------|------|
| ID  | NUMBER |
| CITY | VARCHAR2(21) |
| STATE  | VARCHAR2(2) |
| LAT_N |  NUMBER |
| LONG_W | NUMBER |

where LAT_N is the northern latitude and LONG_W is the western longitude.

**Solution**
```sql
SELECT DISTINCT CITY
FROM STATION
WHERE CITY NOT LIKE 'a%' AND
      CITY NOT LIKE 'e%' AND
      CITY NOT LIKE 'i%' AND
      CITY NOT LIKE 'o%' AND
      CITY NOT LIKE 'u%';    
```


**[Weather Observation Station 10](https://www.hackerrank.com/challenges/weather-observation-station-10/problem)**

Query the list of CITY names from STATION that do not end with vowels. Your result cannot contain duplicates.

Input Format

The STATION table is described as follows:

|  Field | Type |
|------|------|
| ID  | NUMBER |
| CITY | VARCHAR2(21) |
| STATE  | VARCHAR2(2) |
| LAT_N |  NUMBER |
| LONG_W | NUMBER |

where LAT_N is the northern latitude and LONG_W is the western longitude.

**Solution**
```sql
SELECT DISTINCT CITY
FROM STATION
WHERE CITY NOT LIKE '%a' AND
      CITY NOT LIKE '%e' AND
      CITY NOT LIKE '%i' AND
      CITY NOT LIKE '%o' AND
      CITY NOT LIKE '%u';  
```


**[Weather Observation Station 11](https://www.hackerrank.com/challenges/weather-observation-station-11/problem)**

Query the list of CITY names from STATION that either do not start with vowels or do not end with vowels. Your result cannot contain duplicates.

Input Format

The STATION table is described as follows:

|  Field | Type |
|------|------|
| ID  | NUMBER |
| CITY | VARCHAR2(21) |
| STATE  | VARCHAR2(2) |
| LAT_N |  NUMBER |
| LONG_W | NUMBER |

where LAT_N is the northern latitude and LONG_W is the western longitude.

**Solution**
```sql
SELECT DISTINCT CITY
FROM STATION
WHERE (CITY NOT LIKE '%a' AND
      CITY NOT LIKE '%e' AND
      CITY NOT LIKE '%i' AND
      CITY NOT LIKE '%o' AND
      CITY NOT LIKE '%u') 
                        OR (CITY NOT LIKE 'a%' AND
                            CITY NOT LIKE 'e%' AND
                            CITY NOT LIKE 'i%' AND
                            CITY NOT LIKE 'o%' AND
                            CITY NOT LIKE 'u%'
                            );  
```



**[Weather Observation Station 12](https://www.hackerrank.com/challenges/weather-observation-station-12/problem)**

Query the list of CITY names from STATION that do not start with vowels and do not end with vowels. Your result cannot contain duplicates.

Input Format

The STATION table is described as follows:

|  Field | Type |
|------|------|
| ID  | NUMBER |
| CITY | VARCHAR2(21) |
| STATE  | VARCHAR2(2) |
| LAT_N |  NUMBER |
| LONG_W | NUMBER |

where LAT_N is the northern latitude and LONG_W is the western longitude.

**Solution**
```sql
SELECT DISTINCT CITY
FROM STATION
WHERE (CITY NOT LIKE '%a' AND
      CITY NOT LIKE '%e' AND
      CITY NOT LIKE '%i' AND
      CITY NOT LIKE '%o' AND
      CITY NOT LIKE '%u') 
                        AND (CITY NOT LIKE 'a%' AND
                            CITY NOT LIKE 'e%' AND
                            CITY NOT LIKE 'i%' AND
                            CITY NOT LIKE 'o%' AND
                            CITY NOT LIKE 'u%'
                            );    
```



**[Higher Than 75 marks](https://www.hackerrank.com/challenges/more-than-75-marks/problem)**

Query the Name of any student in STUDENTS who scored higher than 75 Marks. Order your output by the last three characters of each name. If two or more students both have names ending in the same last three characters (i.e.: Bobby, Robby, etc.), secondary sort them by ascending ID.

Input Format

The STUDENTS table is described as follows:

|  Column | Type |
|---|---|
| ID  | INTEGER |
| NAME | STRING |
| MARKS  | INTEGER |


The Name column only contains uppercase (A-Z) and lowercase (a-z) letters.

Sample Input

|  ID | NAME | MARKS |
|---|---|----|
| 1  | ASHLEY | 81 | 
| 2 | SAMANTHA   | 75 |
| 4  | JULIA  |  76 |
| 3  | JULIA  |  84 |

Sample Output

Ashley
Julia
Belvet

Explanation

Only Ashley, Julia, and Belvet have Marks > 75. If you look at the last three characters of each of their names, there are no duplicates and 'ley' < 'lia' < 'vet'.

**Solution**
```sql
SELECT NAME
FROM STUDENTS
WHERE MARKS > 75
ORDER BY RIGHT(NAME,3) ASC, ID  
```



