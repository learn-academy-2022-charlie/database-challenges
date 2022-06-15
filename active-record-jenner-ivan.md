# Challenge: Rolodex
- As a developer, I have been tasked with creating a database model that will be used in a rolodex application. I want to ensure that the database behaves as expected and the necessary actions can be performed on the database instances.

## Set Up

- Create a new Rails app named 'rolodex_challenge'.
- Create the database. The output in the terminal should look like this:

```
Created database 'rolodex_challenge_development'
Created database 'rolodex_challenge_test'
```

- Generate a model called Person with a first_name, last_name, and phone. All fields should be strings.

```
rolodex_challenge git:(main) ✗ rails generate model Person first_name:string last_name:string phone:integer
      invoke  active_record
      create    db/migrate/20220609234624_create_people.rb
      create    app/models/person.rb
```

- Run a migration to set up the database.

```
 rolodex_challenge git:(main) ✗ rails db:migrate
== 20220609234624 CreatePeople: migrating =====================================
-- create_table(:people)
   -> 0.0256s
== 20220609234624 CreatePeople: migrated (0.0258s) ============================

```

- Open up Rails console.

```
➜  rolodex_challenge git:(main) ✗ rails console
Loading development environment (Rails 7.0.3)
```

## Actions

- Add five family members into the Person table in the Rails console.

```
3.0.0 :001 > Person.create first_name:'Peter', last_name:'Griffin', phone:111111
1
3.0.0 :002 > Person.create first_name:'Lois', last_name:'Griffin', phone:6969699
3.0.0 :003 > Person.create first_name:'Meg', last_name:'Griffin', phone:77777777
77
3.0.0 :005 > Person.create first_name:'Stewie', last_name:'Griffin', phone:77777
7
3.0.0 :006 > Person.create first_name:'Chris', last_name:'Griffin', phone:777777
3.0.0 :008 > Person.create first_name:'Brian', last_name:'Griffin', phone:777777
```

- Retrieve all the items in the database.

```
3.0.0 :009 > get_person = Person.find 6
```

- Add yourself to the Person table.
- Retrieve all the entries that have the same last_name as you.
- Update the phone number of the last entry in the database.
- Retrieve the first_name of the third Person in the database.

## Stretch Challenges

- Update all the family members with the same last_name as you, to have the same phone number as you.
- Remove all family members that do not have your last_name.