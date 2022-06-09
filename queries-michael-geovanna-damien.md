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
Select name, governmentform
FROM country 
WHERE governmentform
LIKE '%epublic'

"Albania"
"Algeria"
"Angola"
"Argentina"
"Armenia"
"Azerbaijan"
"Bangladesh"
"Benin"
"Bolivia"
"Bosnia and Herzegovina"
"Botswana"
"Brazil"
"Bulgaria"
"Burkina Faso"
"Burundi"
"Chile"
"Costa Rica"
"Djibouti"
"Dominica"
"Dominican Republic"
"Ecuador"
"Egypt"
"El Salvador"
"Eritrea"
"South Africa"
"Ethiopia"
"Fiji Islands"
"Philippines"
"Gabon"
"Gambia"
"Georgia"
"Ghana"
"Guatemala"
"Guinea"
"Guinea-Bissau"
"Guyana"
"Haiti"
"Honduras"
"Indonesia"
"India"
"Iraq"
"Iran"
"Ireland"
"Iceland"
"Israel"
"Italy"
"Austria"
"Yemen"
"Yugoslavia"
"Cameroon"
"Cape Verde"
"Kazakstan"
"Kenya"
"Central African Republic"
"China"
"Kyrgyzstan"
"Kiribati"
"Colombia"
"Comoros"
"Congo"
"Congo, The Democratic Republic of the"
"North Korea"
"South Korea"
"Greece"
"Croatia"
"Cuba"
"Cyprus"
"Laos"
"Latvia"
"Lebanon"
"Liberia"
"Lithuania"
"Madagascar"
"Macedonia"
"Malawi"
"Maldives"
"Mali"
"Malta"
"Marshall Islands"
"Mauritania"
"Mauritius"
"Mexico"
"Micronesia, Federated States of"
"Moldova"
"Mongolia"
"Mozambique"
"Myanmar"
"Namibia"
"Nauru"
"Nicaragua"
"Niger"
"Nigeria"
"Cï¿½te dï¿½Ivoire"
"Pakistan"
"Palau"
"Panama"
"Paraguay"
"Peru"
"Portugal"
"Poland"
"Equatorial Guinea"
"France"
"Romania"
"Rwanda"
"Germany"
"Zambia"
"San Marino"
"Sao Tome and Principe"
"Senegal"
"Seychelles"
"Sierra Leone"
"Singapore"
"Slovakia"
"Slovenia"
"Somalia"
"Sri Lanka"
"Sudan"
"Finland"
"Suriname"
"Syria"
"Tajikistan"
"Taiwan"
"Tanzania"
"Togo"
"Trinidad and Tobago"
"Chad"
"Czech Republic"
"Tunisia"
"Turkey"
"Turkmenistan"
"Uganda"
"Ukraine"
"Hungary"
"Uruguay"
"Uzbekistan"
"Belarus"
"Vanuatu"
"Venezuela"
"Russian Federation"
"Vietnam"
"Estonia"
"United States"
"Zimbabwe"

Which countries are some kind of republic and achieved independence after 1945? (HINT: 92 entries)

Select name, governmentform, indepyear
FROM country 
WHERE indepyear > 1945 AND governmentform
LIKE '%epublic'

"Algeria"
"Angola"
"Armenia"
"Azerbaijan"
"Bangladesh"
"Benin"
"Bosnia and Herzegovina"
"Botswana"
"Burkina Faso"
"Burundi"
"Djibouti"
"Dominica"
"Eritrea"
"Fiji Islands"
"Philippines"
"Gabon"
"Gambia"
"Georgia"
"Ghana"
"Guinea"
"Guinea-Bissau"
"Guyana"
"India"
"Israel"
"Cameroon"
"Cape Verde"
"Kazakstan"
"Kenya"
"Central African Republic"
"Kyrgyzstan"
"Kiribati"
"Comoros"
"Congo"
"Congo, The Democratic Republic of the"
"North Korea"
"South Korea"
"Croatia"
"Cyprus"
"Laos"
"Latvia"
"Lithuania"
"Madagascar"
"Macedonia"
"Malawi"
"Maldives"
"Mali"
"Malta"
"Marshall Islands"
"Mauritania"
"Mauritius"
"Micronesia, Federated States of"
"Moldova"
"Mozambique"
"Myanmar"
"Namibia"
"Nauru"
"Niger"
"Nigeria"
"Cï¿½te dï¿½Ivoire"
"Pakistan"
"Palau"
"Equatorial Guinea"
"Rwanda"
"Germany"
"Zambia"
"Sao Tome and Principe"
"Senegal"
"Seychelles"
"Sierra Leone"
"Singapore"
"Slovakia"
"Slovenia"
"Somalia"
"Sri Lanka"
"Sudan"
"Suriname"
"Tajikistan"
"Tanzania"
"Togo"
"Trinidad and Tobago"
"Chad"
"Czech Republic"
"Tunisia"
"Turkmenistan"
"Uganda"
"Ukraine"
"Uzbekistan"
"Belarus"
"Vanuatu"
"Russian Federation"
"Estonia"
"Zimbabwe"

Which countries achieved independence after 1945 and are not some kind of republic? (HINT: 27 entries)

Select name, governmentform, indepyear
FROM country 
WHERE indepyear > 1945
AND NOT 
governmentform 
LIKE '%epublic'

"Antigua and Barbuda"
"United Arab Emirates"
"Bahamas"
"Bahrain"
"Barbados"
"Belize"
"Brunei"
"Grenada"
"Jamaica"
"Jordan"
"Cambodia"
"Kuwait"
"Lesotho"
"Libyan Arab Jamahiriya"
"Malaysia"
"Morocco"
"Oman"
"Papua New Guinea"
"Qatar"
"Saint Kitts and Nevis"
"Saint Lucia"
"Saint Vincent and the Grenadines"
"Solomon Islands"
"Samoa"
"Swaziland"
"Tonga"
"Tuvalu"


ORDER BY
Which fifteen countries have the lowest life expectancy? (HINT: starts with Zambia, ends with Sierra Leonne)

Select name, lifeexpectancy
FROM country 
ORDER BY lifeexpectancy ASC
LIMIT 15 

"Zambia"
"Mozambique"
"Malawi"
"Zimbabwe"
"Angola"
"Botswana"
"Rwanda"
"Swaziland"
"Niger"
"Namibia"
"Uganda"
"Central African Republic"
"Cï¿½te dï¿½Ivoire"
"Ethiopia"
"Sierra Leone"

Which fifteen countries have the highest life expectancy? (HINT: starts with Andorra, ends with Spain)

Select name, lifeexpectancy
FROM country 
WHERE lifeexpectancy > 0
ORDER BY lifeexpectancy DESC
LIMIT 15 

"Andorra"
"Macao"
"San Marino"
"Japan"
"Singapore"
"Australia"
"Switzerland"
"Sweden"
"Hong Kong"
"Canada"
"Iceland"
"Gibraltar"
"Italy"
"Cayman Islands"
"Spain"


Which five countries have the lowest population density (density = population / surfacearea)? (HINT: starts with Greenland)

Select name, population, surfacearea,
surfacearea / population AS population_density
FROM country 
WHERE population > 0 
ORDER BY  population_density DESC
LIMIT 5

"Greenland"
"Svalbard and Jan Mayen"
"Falkland Islands"
"Pitcairn"
"Western Sahara"

Which countries have the highest population density?(HINT: starts with Macao)

Select name, population, surfacearea,
surfacearea / population AS population_density
FROM country 
WHERE population > 0 
ORDER BY  population_density ASC
LIMIT 5

"Macao"
"Monaco"
"Hong Kong"
"Singapore"
"Gibraltar"

Which is the smallest country by area? (HINT: .4)

Select name, surfacearea
FROM country 
ORDER BY  surfacearea 
LIMIT 1

"Holy See (Vatican City State)"


Which is the smallest country by population? (HINT: 50)?

Select name, population
FROM country 
WHERE population > 0
ORDER BY population 
LIMIT 1

"Pitcairn" 

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