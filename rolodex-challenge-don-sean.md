# Challenge: Rolodex

As a developer, I have been tasked with creating a database model that will be used in a rolodex application. I want to ensure that the database behaves as expected and the necessary actions can be performed on the database instances.

## Set Up

### Create a new Rails app named 'rolodex_challenge'.
```
$ rails new rolodex_challenge -d postgresql -T
```
> Completed 200 OK in 11ms (Views: 4.2ms | ActiveRecord: 0.0ms | Allocations: 7081)  

### Create the database. The output in the terminal should look like this:
>Database 'rolodex_challenge_development'  
>Database 'rolodex_challenge_test'  
```
                                             List of databases
             Name              |    Owner     | Encoding | Collate | Ctype |       Access privileges       
-------------------------------+--------------+----------+---------+-------+-------------------------------
 countries                     | learnacademy | UTF8     | C       | C     | 
 learnacademy                  | learnacademy | UTF8     | C       | C     | 
 postgres                      | learnacademy | UTF8     | C       | C     | 
 rolodex_challenge_development | learnacademy | UTF8     | C       | C     | 
 rolodex_challenge_test        | learnacademy | UTF8     | C       | C     | 
 template0                     | learnacademy | UTF8     | C       | C     | =c/learnacademy              +
                               |              |          |         |       | learnacademy=CTc/learnacademy
 template1                     | learnacademy | UTF8     | C       | C     | =c/learnacademy              +
                               |              |          |         |       | learnacademy=CTc/learnacademy
(7 rows)
```
### Generate a model called Person with a first_name, last_name, and phone. All fields should be strings.
```
$ rails generate model Person first_name:string last_name:string phone:string
```
      invoke  active_record
      create    db/migrate/20220610050628_create_people.rb
      create    app/models/person.rb


### Run a migration to set up the database.
```
$ rails db:migrate
```
>== 20220610050628 CreatePeople: migrating =====================================  
>-- create_table(:people)  
>   -> 0.0080s  
>== 20220610050628 CreatePeople: migrated (0.0080s) ============================  

### Open up Rails console.
```
$ rails c
```
## Actions

### Add five family members into the Person table in the Rails console.
```ruby
Person.create first_name:"Don", last_name:"TheDon", phone:"1234567890"
Person.create first_name:"Sean", last_name:"ManMountain", phone:"7894561234"
Person.create first_name:"Collin", last_name:"BadLuckWithComputers", phone:"4561237896"
Person.create first_name:"Michael", last_name:"TurnDownForWhat", phone:"9841567896"
Person.create first_name:"Valerie", last_name:"Mouse", phone:"4897561236"
Person.create first_name:"Mary", last_name:"NoCamera", phone:"4896517564"



```

Retrieve all the items in the database.
```ruby
Person.all
```

```ruby
[#<Person:0x0000000142434bb0                                  
  id: 2,                                                      
  first_name: "Don",                                          
  last_name: "TheDon",                                        
  phone: "1234567890",                                        
  created_at: Fri, 10 Jun 2022 06:36:14.676105000 UTC +00:00, 
  updated_at: Fri, 10 Jun 2022 06:36:14.676105000 UTC +00:00>,
 #<Person:0x0000000142434a48                                  
  id: 3,                                                      
  first_name: "Sean",                                         
  last_name: "ManMountain",                                   
  phone: "7894561234",                                        
  created_at: Fri, 10 Jun 2022 06:36:39.084471000 UTC +00:00, 
  updated_at: Fri, 10 Jun 2022 06:36:39.084471000 UTC +00:00>,
 #<Person:0x0000000142434908
  id: 4,
  first_name: "Collin",
  last_name: "BadLuckWithComputers",
  phone: "4561237896",
  created_at: Fri, 10 Jun 2022 06:36:42.324561000 UTC +00:00,
  updated_at: Fri, 10 Jun 2022 06:36:42.324561000 UTC +00:00>,
 #<Person:0x0000000142434840
  id: 5,
  first_name: "Michael",
  last_name: "TurnDownForWhat",
  phone: "9841567896",
  created_at: Fri, 10 Jun 2022 06:37:15.025145000 UTC +00:00,
  updated_at: Fri, 10 Jun 2022 06:37:15.025145000 UTC +00:00>,
 #<Person:0x0000000142434750
  id: 6,
  first_name: "Valerie",
  last_name: "Mouse",
  phone: "4897561236",
  created_at: Fri, 10 Jun 2022 06:37:25.580983000 UTC +00:00,
  updated_at: Fri, 10 Jun 2022 06:37:25.580983000 UTC +00:00>,
 #<Person:0x0000000142434660
  id: 7,
  first_name: "Mary",
  last_name: "NoCamera",
  phone: "4896517564",
  created_at: Fri, 10 Jun 2022 06:37:37.120385000 UTC +00:00,
  updated_at: Fri, 10 Jun 2022 06:37:37.120385000 UTC +00:00>] 
```
### Add yourself to the Person table.
- way ahead of you chief
### Retrieve all the entries that have the same last_name as you.
```ruby
Person.where(last_name:"TheDon")
  Person Load (0.2ms)  SELECT "people".* FROM "people" WHERE "people"."last_name" = $1  [["last_name", "TheDon"]]
 =>                                                           
[#<Person:0x0000000142103e00                                  
  id: 2,                                                      
  first_name: "Don",                                          
  last_name: "TheDon",                                        
  phone: "1234567890",                                        
  created_at: Fri, 10 Jun 2022 06:36:14.676105000 UTC +00:00, 
```

### Update the phone number of the last entry in the database.
I updated everyone's phone number, but to update the last number
1. store the last entry as a variable
```ruby
last_entry = Person.last
```
2. use method on variable last_entry
```ruby
last_entry.update phone:"777-777-7777"
```

```ruby
phone_update.update phone:"555-555-5555"
  TRANSACTION (1.4ms)  BEGIN
  Person Update (5.9ms)  UPDATE "people" SET "phone" = $1, "updated_at" = $2 WHERE "people"."id" = $3  [["phone", "555-555-5555"], ["updated_at", "2022-06-10 06:42:39.730606"], ["id", 2]]
  TRANSACTION (0.5ms)  COMMIT                                                
  TRANSACTION (0.2ms)  BEGIN                                                 
  Person Update (0.3ms)  UPDATE "people" SET "phone" = $1, "updated_at" = $2 WHERE "people"."id" = $3  [["phone", "555-555-5555"], ["updated_at", "2022-06-10 06:42:39.741715"], ["id", 3]]
  TRANSACTION (0.2ms)  COMMIT                                                
  TRANSACTION (0.1ms)  BEGIN                                                 
  Person Update (0.2ms)  UPDATE "people" SET "phone" = $1, "updated_at" = $2 WHERE "people"."id" = $3  [["phone", "555-555-5555"], ["updated_at", "2022-06-10 06:42:39.743707"], ["id", 4]]
  TRANSACTION (0.2ms)  COMMIT                                                
  TRANSACTION (0.1ms)  BEGIN                                                 
  Person Update (0.2ms)  UPDATE "people" SET "phone" = $1, "updated_at" = $2 WHERE "people"."id" = $3  [["phone", "555-555-5555"], ["updated_at", "2022-06-10 06:42:39.745171"], ["id", 5]]
  TRANSACTION (0.2ms)  COMMIT                                    
  TRANSACTION (0.1ms)  BEGIN                                     
  Person Update (0.2ms)  UPDATE "people" SET "phone" = $1, "updated_at" = $2 WHERE "people"."id" = $3  [["phone", "555-555-5555"], ["updated_at", "2022-06-10 06:42:39.746385"], ["id", 6]]
  TRANSACTION (0.2ms)  COMMIT                                    
  TRANSACTION (0.1ms)  BEGIN
  Person Update (0.2ms)  UPDATE "people" SET "phone" = $1, "updated_at" = $2 WHERE "people"."id" = $3  [["phone", "555-555-5555"], ["updated_at", "2022-06-10 06:42:39.747522"], ["id", 7]]
  TRANSACTION (0.3ms)  COMMIT
 => 
[#<Person:0x00000001426c4470
  id: 2,
  first_name: "Don",
  last_name: "TheDon",
  phone: "555-555-5555",
  created_at: Fri, 10 Jun 2022 06:36:14.676105000 UTC +00:00,
  updated_at: Fri, 10 Jun 2022 06:42:39.730606000 UTC +00:00>,
 #<Person:0x00000001426bfe70
  id: 3,
  first_name: "Sean",
  last_name: "ManMountain",
  phone: "555-555-5555",
  created_at: Fri, 10 Jun 2022 06:36:39.084471000 UTC +00:00,
  updated_at: Fri, 10 Jun 2022 06:42:39.741715000 UTC +00:00>,
 #<Person:0x00000001426bfc68
  id: 4,
  first_name: "Collin",
  last_name: "BadLuckWithComputers",
  phone: "555-555-5555",
  created_at: Fri, 10 Jun 2022 06:36:42.324561000 UTC +00:00,
  updated_at: Fri, 10 Jun 2022 06:42:39.743707000 UTC +00:00>,
 #<Person:0x00000001426bfb78
  id: 5,
  first_name: "Michael",
  last_name: "TurnDownForWhat",
  phone: "555-555-5555",
  created_at: Fri, 10 Jun 2022 06:37:15.025145000 UTC +00:00,
  updated_at: Fri, 10 Jun 2022 06:42:39.745171000 UTC +00:00>,
 #<Person:0x00000001426bfab0
  id: 6,
  first_name: "Valerie",
  last_name: "Mouse",
  phone: "555-555-5555",
  created_at: Fri, 10 Jun 2022 06:37:25.580983000 UTC +00:00,
  updated_at: Fri, 10 Jun 2022 06:42:39.746385000 UTC +00:00>,
 #<Person:0x00000001426bf9e8
  id: 7,
  first_name: "Mary",
  last_name: "NoCamera",
  phone: "555-555-5555",
  created_at: Fri, 10 Jun 2022 06:37:37.120385000 UTC +00:00,
  updated_at: Fri, 10 Jun 2022 06:42:39.747522000 UTC +00:00>] 
```

### Retrieve the first_name of the third Person in the database.
```ruby
third_person = Person.third
  Person Load (0.3ms)  SELECT "people".* FROM "people" ORDER BY "people"."id" ASC LIMIT $1 OFFSET $2  [["LIMIT", 1], ["OFFSET", 2]]
 =>                                                                            
#<Person:0x00000001421a9d50                                                    
...                                                                            
3.0.0 :014 > third_person.last_name
 => "BadLuckWithComputers" 
```

## Stretch Challenges

### Update all the family members with the same last_name as you, to have the same phone number as you.
- to update all family member with the same last_name
1. Store correct query into a variable
```ruby
same_last_name = Person.where(last_name:"TheDon")
```
2. Use method on variable to update phone number
```ruby
same_last_name.update phone:"888-888-8888"
```

### Remove all family members that do not have your last_name.
1. Store people with different last names into a variable
```ruby
different_last_name = Person.where.not(last_name:"TheDon")
```
2. Then use delete method on variable
```ruby
different_last_name.delete
```