<!-- Create three owners and save them in the database

rails g model owner name:string address:string

rails g model credit_card number:integer expiration_date:string owner:string

Owner.create name:"logan", address:"2020 Mockingbird Lane"

Owner.create name:"nic", address:"2021 Mockingbird Lane"

Owner.create name:"sean", address:"2022 Mockingbird Lane"


Create a credit card in the database for each owner
Add two more credit cards to one of the owners
Stretch Challenge
Add a credit limit to each card
Find the total credit extended to the owner with multiple credit cards -->
