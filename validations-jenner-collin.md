Validations Challenges
Create a Rails application called company_contacts. The app will have a PostgreSQL database.

```
rails new company_contacts -d postgresql -T
```

Generate a model called Account that has a username, a password, and an email.
All stories should have accompanying model specs.

```
rails generate model Account username:string password:string email:string
```

Developer Stories

As a developer, I need username, password, and email to be required.

```
app > models > account.rb

validates :username, :password, :email, presence: true
```

As a developer, I need every username to be at least 5 characters long.

```
app > models > account.rb

validates :username, length: { minimum: 5 }
```

As a developer, I need each username to be unique.

```
app > models > account.rb

validates :username, uniqueness: true
```

As a developer, I need each password to be at least 6 characters long.

```
app > models > account.rb

validates :password, length: { minimum: 6 }
```

As a developer, I need each password to be unique.
```
app > models > account.rb

validates :password, uniqueness: true
```

As a developer, I want my Account model to have many associated Addresses.

```ruby
rails generate model Address street_number:string street_name:string city:string state:string zip:string account_id:integer

class Address < ApplicationRecord
    belongs_to :account
end

class Account < ApplicationRecord
    # validates :username, :password, :email, presence: true
    # validates :username, length: { minimum: 5 }
    # validates :username, uniqueness: true
    # validates :password, length: { minimum: 6 }
    # validates :password, uniqueness: true
    has_many: addresses
end

rails db:migrate
```

As a developer, I want Address to have street_number, street_name, city, state, and zip attributes. The street_number and zip should be integers.

```ruby
rails generate migration change_column_datatype  


class ChangeColumnToAddress < ActiveRecord::Migration[7.0]
  def change
    change_column :addresses, :zip, :integer, using: 'zip::integer'
    change_column :addresses, :street_number, :integer, using: 'street_number::integer'
  end
end

rails db:migrate
```

As a developer, I want to validate the presence of all fields on Address.


```ruby
app > models > address.rb

class Address < ApplicationRecord
    # validates :street_number, :street_name, :city, :state, :zip, presence: true
    belongs_to :account
end
```

## Rspec Rails

```ruby
require 'rails_helper'

RSpec.describe Account, type: :model do
  describe 'Account Model' do
    it 'validates that the presence of username is true, and throws an error if it isnt' do
      new_account = Account.create username:nil, password:"Test Password", email:"Test Email"
      expect(new_account.errors[:username]).to_not be_empty
    end

    it 'validates that the presence of password is true, and throws an error if it isnt' do
      new_account = Account.create username:"Test Username", password:nil, email:"Test Email"
      expect(new_account.errors[:password]).to_not be_empty
    end

    it 'validates that the presence of email is true, and throws an error if it isnt' do
      new_account = Account.create username:"Test Username", password:"Test Password", email:nil
      expect(new_account.errors[:email]).to_not be_empty
    end

    it 'validates the length of username is more than 5 characters and throws an error if it isnt' do
      new_account = Account.create username:"Test", password:"Test Password", email:"Test Email"
      expect(new_account.errors[:username]).to_not be_empty
    end

    it 'validates the length of password is more than 6 characters and throws an error if it isnt' do
      new_account = Account.create username:"Test", password:"Passd", email:"Test Email"
      expect(new_account.errors[:password]).to_not be_empty
    end

    it 'validates if a username is unique and throws an error if it isnt' do
      Account.create(username:"Testas", password:"Passdad", email:"Test Email")
      new_account = Account.create(username:"Testas", password:"Passdw", email:"Test Email")
      expect(new_account.errors[:username]).to_not be_empty
    end

    it 'validates if a password is unique and throws an error if it isnt' do
      Account.create(username:"Tests4", password:"Passdad", email:"Test Email")
      new_account = Account.create username:"Testr44", password:"Passdad", email:"Test Email"
      expect(new_account.errors[:password]).to_not be_empty
    end

    end
end

```

Stretch Challenges
As a developer, I need each Account password to have at least one number.
HINT: Read about custom validations in the Active Record validation docs.
As a developer, I want to validate that Address street_number, street_name, zip are unique for within an account.
HINT: Read about :scope in the Active Record validation docs.
As a developer, I want to validate that the Address street_number and zip are numbers.
HINT: Read about numericality in the Active Record validation docs.
As a developer, I want to see a custom error message that says "Please, input numbers only" if street_number or zip code are not numbers.
