WHERE
What is the population of the US? (HINT: 278357000)

SELECT name, population
FROM country
WHERE name = 'United States'

> 278357000

What is the area of the US? (HINT: 9.36352e+06)

SELECT name, surfacearea
FROM country
WHERE name = 'United States'

> 9.36352e+06

Which countries gained their independence before 1963?

SELECT name, indepyear
FROM country
WHERE indepyear < 1963
ORDER BY indepyear DESC

>"Jamaica"
"Uganda"
"Burundi"
"Rwanda"
"Samoa"
"Trinidad and Tobago"
"Algeria"
"Kuwait"
"Tanzania"
"Sierra Leone"
"Mali"
"Senegal"
"Central African Republic"
"Cï¿½te dï¿½Ivoire"
"Cyprus"
"Madagascar"
"Chad"
"Benin"
"Togo"
"Congo, The Democratic Republic of the"
"Congo"
"Burkina Faso"
"Somalia"
"Gabon"
"Cameroon"
"Mauritania"
"Niger"
"Nigeria"
"Guinea"
"Ghana"
"Malaysia"
"Sudan"
"Morocco"
"Tunisia"
"Germany"
"Laos"
"Cambodia"
"Oman"
"Libyan Arab Jamahiriya"
"Israel"
"Myanmar"
"North Korea"
"South Korea"
"Sri Lanka"
"India"
"Pakistan"
"Philippines"
"Jordan"
"Vietnam"
"Indonesia"
"Taiwan"
"Iceland"
"Lebanon"
"Syria"
"Saudi Arabia"
"Iraq"
"Holy See (Vatican City State)"
"Turkey"
"Egypt"
"Mongolia"
"Ireland"
"Afghanistan"
"Poland"
"Yugoslavia"
"Yemen"
"Austria"
"Hungary"
"Finland"
"Albania"
"South Africa"
"Bhutan"
"Bulgaria"
"New Zealand"
"Iran"
"Norway"
"Panama"
"Cuba"
"Australia"
"Romania"
"Canada"
"Luxembourg"
"Italy"
"Monaco"
"Liberia"
"Dominican Republic"
"El Salvador"
"Honduras"
"Nicaragua"
"Belgium"
"Greece"
"Uruguay"
"Bolivia"
"Ecuador"
"Brazil"
"Costa Rica"
"Guatemala"
"Peru"
"Argentina"
"Paraguay"
"Venezuela"
"Chile"
"Colombia"
"Mexico"
"Liechtenstein"
"Haiti"
"United States"
"Nepal"
"Netherlands"
"Switzerland"
"Spain"
"Thailand"
"Andorra"
"Portugal"
"United Kingdom"
"San Marino"
"France"
"Sweden"
"Denmark"
"Japan"
"Ethiopia"
"China"

List the countries in Africa that have a population smaller than 30,000,000 and a life expectancy of more than 45? (HINT: 37 entries)

SELECT name, population, lifeexpectancy
FROM country
WHERE continent = 'Africa' AND population < 30000000 AND lifeexpectancy > 45
ORDER BY name

> "Benin"
"Burkina Faso"
"Burundi"
"Cameroon"
"Cape Verde"
"Chad"
"Comoros"
"Congo"
"Cï¿½te dï¿½Ivoire"
"Djibouti"
"Equatorial Guinea"
"Eritrea"
"Gabon"
"Gambia"
"Ghana"
"Guinea"
"Guinea-Bissau"
"Lesotho"
"Liberia"
"Libyan Arab Jamahiriya"
"Madagascar"
"Mali"
"Mauritania"
"Mauritius"
"Mayotte"
"Morocco"
"Rï¿½union"
"Saint Helena"
"Sao Tome and Principe"
"Senegal"
"Seychelles"
"Sierra Leone"
"Somalia"
"Sudan"
"Togo"
"Tunisia"
"Western Sahara"

Which countries are something like a republic? (HINT: Are there 122 or 143?)

Which countries are some kind of republic and achieved independence after 1945? (HINT: 92 entries)

Which countries achieved independence after 1945 and are not some kind of republic? (HINT: 27 entries)


ORDER BY
Which fifteen countries have the lowest life expectancy? (HINT: starts with Zambia, ends with Sierra Leonne)
Which fifteen countries have the highest life expectancy? (HINT: starts with Andorra, ends with Spain)
Which five countries have the lowest population density (density = population / surfacearea)? (HINT: starts with Greenland)
Which countries have the highest population density?(HINT: starts with Macao)
Which is the smallest country by area? (HINT: .4)
Which is the smallest country by population? (HINT: 50)?
Which is the biggest country by area? (HINT: 1.70754e+07)
Which is the biggest country by population? (HINT: 1277558000)
Who is the most influential head of state measured by population? (HINT: Jiang Zemin)
Subqueries: WITH
Of the countries with the top 10 gnp, which has the smallest population? (HINT: Canada)
Of the 10 least populated countries with permament residents (a non-zero population), which has the largest surfacearea? (HINT: Svalbard and Jan Mayen)
Aggregate Functions: GROUP BY
Which region has the highest average gnp? (HINT: North America)
Who is the most influential head of state measured by surface area? (HINT: Elisabeth II)
What is the average life expectancy for all continents?
What are the most common forms of government? (HINT: use count(*))
How many countries are in North America?
What is the total population of all continents?


Stretch Challenges
Which countries have the letter ‘z’ in the name? How many?
Of the smallest 10 countries by area, which has the biggest gnp? (HINT: Macao)
Of the smallest 10 countries by population, which has the biggest per capita gnp?
Of the biggest 10 countries by area, which has the biggest gnp?
Of the biggest 10 countries by population, which has the biggest per capita gnp?
What is the sum of surface area of the 10 biggest countries in the world? The 10 smallest?
What year is this country database from? Cross reference various pieces of information to determine the age of this database.