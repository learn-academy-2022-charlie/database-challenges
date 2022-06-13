Banking Challenge
Setup
Create a new rails application and database
<!-- rails new Bank_Associations -d postgresql -T -->
<!-- cd Bank_Associations    -->
<!-- rails db:create   -->

Create a model for owner
An owner has a name and address, and can have multiple credit cards
<!-- rails generate model Owner name:string adress:string number_of_creditcards:integer  -->

Create a model for credit card

A credit card has a number, an expiration date, and an owner
Challenges
<!-- rails generate model CreditCard number:string expiration_date:string owner_id:integer -->

Create three owners and save them in the database
<!-- 
1) Owner.create name:"Jenner", adress:"5555 market st", number_of_cred

2) Owner.create name:"Collin", adress:"2424 market st", number_of_cred
itcards: 0 

3) Owner.create name:"Wayne", adress:"7184 sd dr", number_of_creditcar
ds: 0 
-->

Create a credit card in the database for each owner
<!-- 
Jenner = Owner.first
Jenner.credit_cards.create number: "5757455463637272", expiration_date: "07/24/1997" -->

<!-- 
Collin = Owner.second
Collin.credit_cards.create number: "7777777777777777", expiration_date: "08/24/77" -->

<!-- 
Collin = Owner.third
wayne.credit_cards.create number: "9999999797979797", expiration_date: "08/24/77 -->
Add two more credit cards to one of the owners
Stretch Challenge
Add a credit limit to each card
Find the total credit extended to the owner with multiple credit cards