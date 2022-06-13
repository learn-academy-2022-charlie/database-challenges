Created a rails application called 'validation' (my bad)


generated a database.
Installed RSpec
Created a model called Account. The model takes a username:string, password:string, and email:string.

migrated the database

Validations Challenges
Create a Rails application called company_contacts. The app will have a PostgreSQL database.
Generate a model called Account that has a username, a password, and an email.
All stories should have accompanying model specs.
Developer Stories

As a developer, I need username, password, and email to be required.
As a developer, I need every username to be at least 5 characters long.
As a developer, I need each username to be unique.
As a developer, I need each password to be at least 6 characters long.
As a developer, I need each password to be unique.
As a developer, I want my Account model to have many associated Addresses.
As a developer, I want Address to have street_number, street_name, city, state, and zip attributes. The street_number and zip should be integers.
As a developer, I want to validate the presence of all fields on Address.
Stretch Challenges

As a developer, I need each Account password to have at least one number.
HINT: Read about custom validations in the Active Record validation docs.
As a developer, I want to validate that Address street_number, street_name, zip are unique for within an account.
HINT: Read about :scope in the Active Record validation docs.
As a developer, I want to validate that the Address street_number and zip are numbers.
HINT: Read about numericality in the Active Record validation docs.
As a developer, I want to see a custom error message that says "Please, input numbers only" if street_number or zip code are not numbers.
HINT: Read about message in the validation docs.

wrote rspec test for the challenges:

RSpec.describe Account, type: :model do
  it 'validates username and returns an error message if the username is empty' do 

  end
  it 'validates password and returns an error message if the password is empty' do 

  end
  it 'validates email and returns an error message if the email is empty' do 

  end
  it 'validates username and returns an error message if the username is less than 5 characters long' do 

  end
  it 'validates username and returns an error message if the username is not unique' do 

  end
  it 'validates password and returns an error message if the password is less than 6 characters long' do 

  end
  it 'validates password and returns an error message if the password is not unique' do 

  end
 
end

RSpec.describe Address, type: :model do 
  it 'validates association with Account to be true' do 

  end
  it 'validates street_number  and returns an error message if street_number is left empty' do 

  end
  it 'validates street_name  and returns an error message if street_name is left empty' do 

  end
  it 'validates city  and returns an error message if city is left empty' do 

  end
  it 'validates state  and returns an error message if state is left empty' do 

  end
  it 'validates zip  and returns an error message if zip is left empty' do 

  end
  it 'validates street_number  and returns an error message if street_number is not the type of integer' do 

  end
  it 'validates zip  and returns an error message if zip is not the type of integer' do 

  end
  it 'validates the presence of all fields in Address' do 

  end
end

Got red
F......

Failures:

  1) Account validates username and returns an error message if the username is empty
     Failure/Error: expect(new_account.errors[:username]).to_not be_empty
       expected `[].empty?` to be falsey, got true
     # ./spec/models/account_spec.rb:8:in `block (2 levels) in <top (required)>'

Finished in 0.03094 seconds (files took 0.88924 seconds to load)
7 examples, 1 failure

created the following test:

it 'validates username and returns an error message if the username is empty' do 
    new_account = Account.create username: nil, password:"123456", email:"hello@yahoo.com"

    p new_account.errors[:username]
    expect(new_account.errors[:username]).to_not be_empty
  end
  wrote the following code to validate the test:
  validates :username, presence: true
  got GREEN:

  ➜  validations git:(main) ✗ rspec spec/models/account_spec.rb -fd

Account
["can't be blank"]
  validates username and returns an error message if the username is empty
  validates password and returns an error message if the password is empty
  validates email and returns an error message if the email is empty
  validates username and returns an error message if the username is less than 5 characters long
  validates username and returns an error message if the username is not unique
  validates password and returns an error message if the password is less than 6 characters long
  validates password and returns an error message if the password is not unique

Finished in 0.02499 seconds (files took 0.86056 seconds to load)
7 examples, 0 failures

wrote the test:
it 'validates password and returns an error message if the password is empty' do 
    new_account = Account.create username: "hello", password: nil, email:"hello@yahoo.com"

    p new_account.errors[:password]
    expect(new_account.errors[:password]).to_not be_empty
  end

Got red:
Failures:

  1) Account validates password and returns an error message if the password is empty
     Failure/Error: expect(new_account.errors[:password]).to_not be_empty
       expected `[].empty?` to be falsey, got true
     # ./spec/models/account_spec.rb:14:in `block (2 levels) in <top (required)>'

Finished in 0.03102 seconds (files took 0.87957 seconds to load)
7 examples, 1 failure

Wrote the validation code:

validates :username, :password, presence: true

Got Green:

Account
["can't be blank"]
  validates username and returns an error message if the username is empty
["can't be blank"]
  validates password and returns an error message if the password is empty
  validates email and returns an error message if the email is empty
  validates username and returns an error message if the username is less than 5 characters long
  validates username and returns an error message if the username is not unique
  validates password and returns an error message if the password is less than 6 characters long
  validates password and returns an error message if the password is not unique

Finished in 0.0263 seconds (files took 0.86646 seconds to load)
7 examples, 0 failures

wrote the test:
it 'validates email and returns an error message if the email is empty' do 
    new_account = Account.create username: "hello", password: "12345", email: nil

    p new_account.errors[:email]
    expect(new_account.errors[:email]).to_not be_empty

  end

  Got Red:
  Failures:

  1) Account validates email and returns an error message if the email is empty
     Failure/Error: expect(new_account.errors[:email]).to_not be_empty
       expected `[].empty?` to be falsey, got true
     # ./spec/models/account_spec.rb:20:in `block (2 levels) in <top (required)>'

Finished in 0.03366 seconds (files took 0.86018 seconds to load)
7 examples, 1 failure

Wrote the validation:
class Account < ApplicationRecord
    validates :username, :password, :email, presence: true
end

Got Green:
Account
["can't be blank"]
  validates username and returns an error message if the username is empty
["can't be blank"]
  validates password and returns an error message if the password is empty
["can't be blank"]
  validates email and returns an error message if the email is empty
  validates username and returns an error message if the username is less than 5 characters long
  validates username and returns an error message if the username is not unique
  validates password and returns an error message if the password is less than 6 characters long
  validates password and returns an error message if the password is not unique

Finished in 0.02625 seconds (files took 0.85718 seconds to load)
7 examples, 0 failures

Wrote the test:

 it 'validates username and returns an error message if the username is less than 5 characters long' do 

    new_account = Account.create username: "hell", password: "12345", email: "joe@gmail.com"

    p new_account.errors[:username]
    expect(new_account.errors[:username]).to_not be_empty

  end


Got red:
Failures:

  1) Account validates username and returns an error message if the username is less than 5 characters long
     Failure/Error: expect(new_account.errors[:username]).to_not be_empty
       expected `[].empty?` to be falsey, got true
     # ./spec/models/account_spec.rb:28:in `block (2 levels) in <top (required)>'

Finished in 0.03166 seconds (files took 0.89266 seconds to load)
7 examples, 1 failure

Failed examples:

rspec ./spec/models/account_spec.rb:23 # Account validates username and returns an error message if the username is less than 5 characters long

Wrote the validation:
class Account < ApplicationRecord
    validates :username, :password, :email, presence: true
    validates :username, length: { minimum: 5 }
end


Got Green:
Account
["can't be blank", "is too short (minimum is 5 characters)"]
  validates username and returns an error message if the username is empty
["can't be blank"]
  validates password and returns an error message if the password is empty
["can't be blank"]
  validates email and returns an error message if the email is empty
["is too short (minimum is 5 characters)"]
  validates username and returns an error message if the username is less than 5 characters long
  validates username and returns an error message if the username is not unique
  validates password and returns an error message if the password is less than 6 characters long
  validates password and returns an error message if the password is not unique

Finished in 0.02915 seconds (files took 0.86484 seconds to load)
7 examples, 0 failures

Wrote the test:

it 'validates username and returns an error message if the username is not unique' do 
    Account.create(username: "hello", password: "12345", email: "joe@gmail.com")
    new_account = Account.create username: "Hello", password: "12345", email: "joe@gmail.com"

    p new_account.errors[:username]
    expect(new_account.errors[:username]).to_not be_empty


  end

  Got RED:
  1) Account validates username and returns an error message if the username is not unique
     Failure/Error: expect(new_account.errors[:username]).to_not be_empty
       expected `[].empty?` to be falsey, got true
     # ./spec/models/account_spec.rb:36:in `block (2 levels) in <top (required)>'

Finished in 0.03731 seconds (files took 0.95344 seconds to load)
7 examples, 1 failure

Failed examples:

rspec ./spec/models/account_spec.rb:31 # Account validates username and returns an error message if the username is not unique


Wrote the validation:
class Account < ApplicationRecord
    validates :username, :password, :email, presence: true
    validates :username, length: { minimum: 5 }
    validates :username, uniqueness: { case_sensitive: false }
end

Got GREEN:

Account
["can't be blank", "is too short (minimum is 5 characters)"]
  validates username and returns an error message if the username is empty
["can't be blank"]
  validates password and returns an error message if the password is empty
["can't be blank"]
  validates email and returns an error message if the email is empty
["is too short (minimum is 5 characters)"]
  validates username and returns an error message if the username is less than 5 characters long
["has already been taken"]
  validates username and returns an error message if the username is not unique
  validates password and returns an error message if the password is less than 6 characters long
  validates password and returns an error message if the password is not unique

Finished in 0.0438 seconds (files took 0.80141 seconds to load)
7 examples, 0 failures

Wrote the test:
it 'validates password and returns an error message if the password is less than 6 characters long' do 
    new_account = Account.create username: "hello", password: "12345", email: "joe@gmail.com"

    p new_account.errors[:password]
    expect(new_account.errors[:password]).to_not be_empty
  end

  Got RED:
   Failures:

  1) Account validates password and returns an error message if the password is less than 6 characters long
     Failure/Error: expect(new_account.errors[:password]).to_not be_empty
       expected `[].empty?` to be falsey, got true
     # ./spec/models/account_spec.rb:44:in `block (2 levels) in <top (required)>'

Finished in 0.04077 seconds (files took 0.86458 seconds to load)
7 examples, 1 failure

Wrote the validation:
class Account < ApplicationRecord
    validates :username, :password, :email, presence: true
    validates :username, length: { minimum: 5 }
    validates :password, length: { minimum: 6 }
    validates :username, uniqueness: { case_sensitive: false }
end


AFTER Review we found we had to make all of the other test elements pass each validation. There is a precedence to what error will populate.

Got GREEN:
Account
["can't be blank", "is too short (minimum is 5 characters)"]
  validates username and returns an error message if the username is empty
["can't be blank", "is too short (minimum is 6 characters)"]
  validates password and returns an error message if the password is empty
["can't be blank"]
  validates email and returns an error message if the email is empty
["is too short (minimum is 5 characters)"]
  validates username and returns an error message if the username is less than 5 characters long
["has already been taken"]
  validates username and returns an error message if the username is not unique
["is too short (minimum is 6 characters)"]
  validates password and returns an error message if the password is less than 6 characters long
  validates password and returns an error message if the password is not unique

Finished in 0.03649 seconds (files took 0.84499 seconds to load)
7 examples, 0 failures