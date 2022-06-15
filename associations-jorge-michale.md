Setup
Create a new rails application and database

Create a model for owner
    1968 rails g model Owner name:“string” address:“string”
An owner has a name and address, and can have multiple credit cards
    Owner.create name:“George Lopez”, address:“69420 Burning Bush Ln.” 

Create a model for credit card
     1969 rails g model C_card number:“string” expiry:“string”

A credit card has a number, an expiration date, and an owner
Challenges
Create three owners and save them in the database
Create a credit card in the database for each owner

Owner.find 1
owner1

Owner.find 2
owner2

Owner.find3
owner3

owner1.c_cards.create number:

Add two more credit cards to one of the owners
Stretch Challenge
Add a credit limit to each card
Find the total credit extended to the owner with multiple credit cards