create rails db
```
-rails new banking -d postgresql -T

-cd banking

create database, cd into directory

-rails db:create
 
```

```
-rails generate model Owner name:string address:text
    -this creates the database chart
- we will do the same thing for the credit
```
```
-rails db:migrate
    -once we create the chart we need to migrate it

- rails c

    this will get us into the console



```
```
Owner.create name:"Leo", address:"233 Bankers St Loan City Ca"

- Owner.create name:"Leo", address:"345 Savings St Shark City"

Owner.create name:"Justin", address:"Buther St Max City"
- this creates a key with atributes

-
```
