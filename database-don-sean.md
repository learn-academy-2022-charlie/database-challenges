# Challenges: SQL Country Database
- Save your queries in a file if you want to keep them for posterity.

## WHERE
### What is the population of the US? (HINT: 278357000)

>SELECT *  
>FROM country  
>WHERE code = 'USA'


### What is the area of the US? (HINT: 9.36352e+06)
>SELECT surfacearea  
>FROM country  
>WHERE code = 'USA'  

### Which countries gained their independence before 1963?
>SELECT name, indepyear  
>FROM country  
>WHERE indepyear < 1963  

### List the countries in Africa that have a population smaller than 30,000,000 and a life expectancy of more than 45? (HINT: 37 entries)
>SELECT name, region, lifeexpectancy, population  
>FROM country  
>WHERE population < 3e+7  
>AND lifeexpectancy > 45  
>AND region  
>LIKE '%frica'   


### Which countries are something like a republic? (HINT: Are there 122 or 143?)
>SELECT name, governmentform  
>FROM country  
>WHERE governmentform  
>LIKE '%epublic'  

>This query gives us 143 result, HOWEVER we know that not all governments with republic in their name are actual republics.

### Which countries are some kind of republic and achieved independence after 1945? (HINT: 92 entries)
>SELECT name, governmentform, indepyear  
>FROM country  
>WHERE governmentform  
>LIKE '%epublic'  
>AND indepyear > 1945 

### Which countries achieved independence after 1945 and are not some kind of republic? (HINT: 27 entries)
>SELECT name, governmentform, indepyear  
>FROM country  
>WHERE indepyear > 1945  
>AND NOT  
>governmentform  
>LIKE '%Republic'  

## ORDER BY
### Which fifteen countries have the lowest life expectancy? (HINT: starts with Zambia, ends with Sierra Leonne)
>SELECT *  
>FROM country   
>WHERE lifeexpectancy > 0  
>ORDER BY lifeexpectancy   
>LIMIT 15  

### Which fifteen countries have the highest life expectancy? (HINT: starts with Andorra, ends with Spain)

>SELECT *  
>FROM country   
>WHERE lifeexpectancy > 0  
>ORDER BY lifeexpectancy DESC  
>LIMIT 15  

### Which five countries have the lowest population density (density = population / surfacearea)? (HINT: starts with Greenland)

>SELECT name, population, surfacearea,  
>population / surfacearea as density  
>FROM country  
>WHERE population > 0  
>ORDER BY density  
>limit 5  

### Which countries have the highest population density?(HINT: starts with Macao)
>SELECT name, population, surfacearea,  
>population / surfacearea as density  
>FROM country  
>WHERE population > 0  
>ORDER BY density DESC  
>limit 5  

### Which is the smallest country by area? (HINT: .4)
>SELECT name, surfacearea  
>FROM country  
>ORDER BY surfacearea  
>limit 1  

### Which is the smallest country by population? (HINT: 50)?
>SELECT name, population  
>FROM country  
>WHERE population > 0  
>ORDER BY population  
>limit 1  

### Which is the biggest country by area? (HINT: 1.70754e+07)
>SELECT name, surfacearea  
>FROM country  
>ORDER BY surfacearea DESC  
>limit 1  

### Which is the biggest country by population? (HINT: 1277558000)
>SELECT name, population  
>FROM country  
>ORDER BY population DESC  
>limit 1  


### Who is the most influential head of state measured by population? (HINT: Jiang Zemin)
>SELECT name, population, headofstate  
>FROM country  
>ORDER BY population DESC  
>limit 1  

## Subqueries: WITH
### Of the countries with the top 10 gnp, which has the smallest population? (HINT: Canada)
>WITH top_gnp AS (  
>&ensp;&ensp;SELECT name, gnp, population  
>&ensp;&ensp;FROM country  
>&ensp;&ensp;ORDER BY gnp DESC  
>&ensp;&ensp;limit 10  
>)  
>SELECT *  
>FROM top_gnp  
>ORDER BY population  


### Of the 10 least populated countries with permanent residents (a non-zero population), which has the largest surfacearea? (HINT: Svalbard and Jan Mayen)
>WITH least_pop AS (  
>&ensp;&ensp;SELECT name, population, surfacearea  
>&ensp;&ensp;FROM country  
>&ensp;&ensp;WHERE population > 0  
>&ensp;&ensp;ORDER BY population  
>&ensp;&ensp;limit 10  
>)  
>SELECT *  
>FROM least_pop  
>ORDER BY surfacearea DESC  
## Aggregate Functions: GROUP BY
### Which region has the highest average gnp? (HINT: North America)
>SELECT region, AVG(gnp)  
>FROM country  
>GROUP BY region  
>ORDER BY avg DESC  

### Who is the most influential head of state measured by surface area? (HINT: Elisabeth II)
>SELECT headofstate, sum(surfacearea)  
>FROM country  
>GROUP BY headofstate  
>ORDER BY sum DESC  

### What is the average life expectancy for all continents?
>SELECT continent, AVG(lifeexpectancy)  
>FROM country  
>GROUP BY continent  

### What are the most common forms of government? (HINT: use count(*))
>SELECT governmentform, COUNT(*)  
>FROM country  
>GROUP BY governmentform  
>ORDER BY count DESC  


### How many countries are in North America?
>SELECT region, COUNT(*)  
>FROM country  
>WHERE region='North America'  
>GROUP BY region  

### What is the total population of all continents?
>SELECT SUM(population)  
>FROM country  

-or  

>SELECT continent, SUM(population)  
>FROM country  
>GROUP BY continent  


# Stretch Challenges
### Which countries have the letter ‘z’ in the name? How many?

### Of the smallest 10 countries by area, which has the biggest gnp? (HINT:  Macao)
### Of the smallest 10 countries by population, which has the biggest per capita gnp?
### Of the biggest 10 countries by area, which has the biggest gnp?
### Of the biggest 10 countries by population, which has the biggest per capita gnp?
### What is the sum of surface area of the 10 biggest countries in the world? The 10 smallest?
### What year is this country database from? Cross reference various pieces of information to determine the age of this database.