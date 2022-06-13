Banking Challenge
Setup
Create a new rails application and database
rails new banking -d postgresql -T
cd banking
rails db:create
rails s
control c to exit

In repo folder
Create a model for owner
An owner has a name and address, and can have multiple credit cards
rails g model Owner name:string address:string
rails db:migrate

Create a model for credit card
A credit card has a number, an expiration date, and an owner
rails g model CreditCard number:string expiration:string owner_id:integer
rails db:migrate

Challenges
Open new terminal for rails console
Create three owners and save them in the database
Owner.create name:"John Smith", address:"123 Elm Street"
Owner.create name:"Jeff Scott", address:"168 Sesame Street"
Owner.create name:"John Smith", address:"123 Elm Street"

Create a credit card in the database for each owner
john = Owner.first
john.credit_cards.create number:"4234 5000 4890 3401", expiration:"Feb 2027"

jeff = Owner.find 2
jeff.credit_cards.create number:"4333 5020 4891 3681", expiration:"Feb 2023"

john = Owner.find 3
john.credit_cards.create number:"7777 6660 8884 2333", expiration:"Nov 2030"

Add two more credit cards to one of the owners
john.credit_cards.create number:"2656 4588 3390 3555", expiration:"Dec 2025"
john.credit_cards.create number:"2221 4099 6663 2116", expiration:"May 2029"


Stretch Challenge
Add a credit limit to each card
rails g migration add_column_credit_limit_to_credit_card

Find the total credit extended to the owner with multiple credit cards