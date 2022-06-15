## Set Up

Create a new Rails app named 'rolodex_challenge'.
> rails new rolodex_challenge -d postgresql -T

Create the database. The output in the terminal should look like this:
Created database 'rolodex_development'
Created database 'rolodex_test'

## Set-up

- Generate a model called Person with a first_name, last_name, and phone. All fields should be strings.
> rails generate model Person first_name:string last_name:string phone:string

- Run a migration to set up the database.
> rails db:migrate

- Open up Rails console.
> rails c


## Actions

- Add five family members into the Person table in the Rails console.
> Person.create first_name: 'Will', last_name: 'Smith', phone: '555-555-5555'
Person.create first_name: 'Oprah', last_name: 'Winfrey', phone: '555-555-5556'
Person.create first_name: 'Tom', last_name: 'Hanks', phone: '555-555-5557'
Person.create first_name: 'Britney', last_name: 'Spears', phone: '555-555-5558'
Person.create first_name: 'Betty', last_name: 'White', phone: '555-556-5555'
Person.create first_name: 'Katie', last_name: 'Richcreek', phone: '555-556-5555'
Person.create first_name: 'Dominique', last_name: 'Richcreek', phone: '555-556-5555'

- Retrieve all the items in the database.
> Person.all

- Add yourself to the Person table.
>  Person.create first_name: 'Damien', last_name: 'Richcreek', phone: '555-555-5515'

- Retrieve all the entries that have the same last_name as you.
> Person.where last_name: 'Richcreek'

- Update the phone number of the last entry in the database.
> damien_phone = Person.last
> damien_phone.phone = '555-555-6666'
> damien_phone.save

- Retrieve the first_name of the third Person in the database.
> Person.third.first_name
> Output: "Tom"


## Stretch Challenges

- Update all the family members with the same last_name as you, to have the same phone number as you.
> 

- Remove all family members that do not have your last_name.
> 
