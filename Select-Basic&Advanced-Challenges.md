**BASIC SELECTS**

**[Revising the Select Query-1](https://www.hackerrank.com/challenges/revising-the-select-query)**


Query all columns for all American cities in CITY with populations larger than 100,000. The CountryCode for America is USA.

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
```
ABC 3 

PQRS 4
```
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

The STUDENTS table is described as follows:

|  Column | Type |
|------|------|
| ID  | INTEGER |
| NAME | STRING |
| MARKS  | INTEGER |


The Name column only contains uppercase (A-Z) and lowercase (a-z) letters.

Sample Input

|  ID | NAME | MARKS |
|------|------|------|
| 1  | ASHLEY | 81 | 
| 2 | SAMANTHA | 75 |
| 4  | JULIA  |  76 |
| 3  | JULIA  |  84 |

Sample Output
```
Ashley
Julia
Belvet
```
Explanation

Only Ashley, Julia, and Belvet have Marks > 75. If you look at the last three characters of each of their names, there are no duplicates and 'ley' < 'lia' < 'vet'.

**Solution**
```sql
SELECT NAME
FROM STUDENTS
WHERE MARKS > 75
ORDER BY RIGHT(NAME,3) ASC, ID  
```



**[Employee Names](https://www.hackerrank.com/challenges/name-of-employees/problem)**

Write a query that prints a list of employee names (i.e.: the name attribute) from the Employee table in alphabetical order.

The Employee table containing employee data for a company is described as follows:

|  Column | Type |
|------|------|
| employee_id  | INTEGER |
| name | STRING |
| months | INTEGER |
| salary | INTEGER |

where employee_id is an employee's ID number, name is their name, months is the total number of months they've been working for the company, and salary is their monthly salary.

Sample Input

|  employee_id | name | marks | salary  |
|------|------|------|------|
| 12228 | Rose | 15 | 1968 |
| 33645 | Angela   | 1 | 3443 |
| 45692  | Frank  | 17  | 1608  |
| 56118  | Patrick  |  7 | 1345
| 59725 | Lisa | 11 | 2330 |
| 74197 | Kimberly   | 16 | 4372 |
| 78454  | Bonnie  |  8 | 1771 |
| 83565 | Michael |  6 | 2017
| 98607  | Todd  |  5 | 3396 |
| 99989 | Joe |  9 | 3573 |

Sample Output
```
Angela
Bonnie
Frank
Joe
Kimberly
Lisa
Michael
Patrick
Rose
Todd
```
**Solution**
```sql
SELECT NAME
FROM EMPLOYEE
ORDER BY NAME ASC; 
```


**[Employee Salaries](https://www.hackerrank.com/challenges/salary-of-employees/problem)**

Write a query that prints a list of employee names (i.e.: the name attribute) for employees in Employee having a salary greater than $2000 per month who have been employees for less than 10 months. Sort your result by ascending employee_id.

The Employee table containing employee data for a company is described as follows:

|  Column | Type |
|------|------|
| employee_id  | INTEGER |
| name | STRING |
| months | INTEGER |
| salary | INTEGER |

where employee_id is an employee's ID number, name is their name, months is the total number of months they've been working for the company, and salary is the their monthly salary.

|  employee_id | name | marks | salary  |
|-----|------|----|-----|
| 12228 | Rose | 15 | 1968 |
| 33645 | Angela   | 1 | 3443 |
| 45692  | Frank  | 17  | 1608 |
| 56118  | Patrick  |  7 | 1345
| 59725 | Lisa | 11 | 2330 |
| 74197 | Kimberly   | 16 | 4372 |
| 78454  | Bonnie  |  8 | 1771 |
| 83565 | Michael |  6 | 2017
| 98607  | Todd  |  5 | 3396 |
| 99989 | Joe |  9 | 3573 |

Sample Output
```
Angela
Michael
Todd
Joe
```
Explanation

Angela has been an employee for 1 month and earns $3443 per month.    
Michael has been an employee for 6 months and earns $2017 per month.    
Todd has been an employee for 5 months and earns $3396 per month.     
Joe has been an employee for 9 months and earns $3573 per month.    
We order our output by ascending employee_id.

**Solution**
```sql
SELECT NAME
FROM EMPLOYEE
WHERE SALARY > 2000 AND MONTHS < 10
ORDER BY EMPLOYEE_ID ASC;
```

**ADVANCED SELECTS**

**[Type of Triangle](https://www.hackerrank.com/challenges/what-type-of-triangle/problem)**

Write a query identifying the type of each record in the TRIANGLES table using its three side lengths. Output one of the following statements for each record in the table:

**Equilateral**: It's a triangle with  sides of equal length.    
**Isosceles**: It's a triangle with  sides of equal length.    
**Scalene**: It's a triangle with  sides of differing lengths.    
**Not A Triangle**: The given values of A, B, and C don't form a triangle.    

The TRIANGLES table is described as follows:

| Column | Type |
|------|------|
| A | *Integer* |
| B | *Integer* | 
| C | *Integer* |

Each Row in the table denotes the lengths of each of a triangle's three sides.

Sample Input

| A | B | C | 
|----|----|----|
| 20 | 20 | 23 | 
| 20 | 20 | 20 |
| 20 | 21 | 22 | 
|13 | 14 | 30 |

Sample Output
```
Isosceles
Equilateral
Scalene
Not A Triangle
```

Explanation 

Values in the tuple (20, 20, 23) form an Isocsceles triangle, because A = B.    
Values in the tuple (20, 20, 20) form an Equilateral triangle, because A = B = C. Values in the tuple (20, 21, 22) form a Scalene triangle, because A ≠ B ≠ C.    
Values in the tuple (13, 14, 30) cannot form a triangle because the combined value of sides A and B is not larger than that of side C.

**Solution**
```sql
SELECT
    CASE
        WHEN A + B <= C THEN 'Not A Triangle'
        WHEN A = B AND B = C THEN 'Equilateral'
        WHEN A = B OR B = C OR C = A THEN 'Isosceles'
        WHEN A <> B  AND B <> C AND C <> A THEN 'Scalene'
    END
FROM TRIANGLES;
```
**[The PADS](https://www.hackerrank.com/challenges/the-pads/problem)**

Generate the following two result sets:

Query an alphabetically ordered list of all names in **OCCUPATIONS**, immediately followed by the first letter of each profession as a parenthetical (i.e.: enclosed in parentheses). For example: AnActorName(A), ADoctorName(D), AProfessorName(P), and ASingerName(S).    
Query the number of ocurrences of each occupation in **OCCUPATIONS**. Sort the occurrences in ascending order, and output them in the following format:

There are a total of (occupation_count) (occupations)s.    
Where (occupation_count) is the number of occurrences of an occupation in OCCUPATIONS and (occupation) is the lowercase occupation name. If more than one Occupation has the same (occupation_count), they should be ordered alphabetically.    
**Note:** There will be at least two entries in the tables for each type of occupation.

The OCCUPATIONS table is described as folows: 
| Column | Type | 
|-----|-----|
| Name | *String* | 
| Occupation | *String* | 
Occupation will only contain one of the following values: **Doctor**, **Professor**, **Singer**, or **Actor**. 

Sample Input

An OCCUPATIONS table that contains the following records: 

| Name | Occupation | 
|-----|-----|
| Samantha | Doctor | 
| Julia | Actor | 
| Maria | Actor | 
| Meera | Singer | 
| Ashely | Professor | 
| Ketty | Professor | 
| Christeen | Professor |
| Jane | Actor | 
| Jenny | Doctor | 
| Priya | Singer | 

Sample Output

```
Ashely(P)
Christeen(P)
Jane(A)
Jenny(D)
Julia(A)
Ketty(P)
Maria(A)
Meera(S)
Priya(S)
Samantha(D)
There are a total of 2 doctors.
There are a total of 2 singers.
There are a total of 3 actors.
There are a total of 3 professors.
```

Explanation    
The results of the first query are formatted to the problem description's specifications.    
The results of the second query are ascendingly ordered first by number of names corresponding to each profession (2 ≤ 2 ≤ 3 ≤ 3), and then alphabetically by profession (doctor ≤ singer, and actor ≤ professor ).

```sql
SELECT CONCAT(NAME, '(', SUBSTR(OCCUPATION,1,1), ')')
FROM OCCUPATIONS
ORDER BY NAME;

SELECT  CONCAT("There are a total of ", COUNT(OCCUPATION), ' ', LOWER(OCCUPATION), 's.')
FROM OCCUPATIONS
GROUP BY OCCUPATION
ORDER BY COUNT(OCCUPATION) ASC, OCCUPATION;
```
