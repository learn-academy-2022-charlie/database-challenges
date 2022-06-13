### Setup

## Validations Challenges

Create a Rails application called company_contacts. The app will have a PostgreSQL database.

```
$ rails new validations -d postgresql -T
$ cd validations
$ rails db:create
```

Create dependencies for RSpec:

```
$ bundle add respec-rails
$ rails generate respec:install
```

```
$ rails db:migrate
$ rails server
```

Generate a model called Account that has a username, a password, and an email.

```
$ rails generate model Account username:string pass:string email:string
$ rails db:migrate
```

All stories should have accompanying model specs.

## Developer Stories

As a developer, I need username, password, and email to be required.

in spec/models/account_spec.rb
```
RSpec.describe Account, type: :model do
  it 'is not valid without a username' do
    scully = Account.create username:nil,
    password:"jfvfvj",email:"carsonn@yahoo.com"
    expect(scully.errors[:username]).to_not be_empty
  end
    it 'is not valid without a password' do
    scully = Account.create username:grouch123,
    password:nil,email:"carsonn@yahoo.com"
    expect(scully.errors[:username]).to_not be_empty
  end
    it 'is not valid without an email' do
    scully = Account.create username:"grouch123",
    password:"jfvfvj",email:nil
    expect(scully.errors[:username]).to_not be_empty
  end
end
```

in account.rb
```
class Account < ApplicationRecord
    validates :username, :password, :email, presence: true
end
```

As a developer, I need every username to be at least 5 characters long.

in spec/models/account_spec.rb
```
    it 'username is not less than 5 characters' do
    scully = Account.create username:"tree",
    password:"jfvfvj",email:"something@gmail.com"
    expect(scully.errors[:username]).to_not be_empty
  end
end
```

in account.rb
```
class Account < ApplicationRecord
    validates :username, :password, :email, presence: true
    validates :username, length { minimum: 5 }
end
```


As a developer, I need each username to be unique.

in spec/models/account_spec.rb
```
    it 'username must be unique' do
        scully = Account.create username:"tree",
        password:"gnuern4",email:"vgdg@yahoo.com";
        molder = Account.create username:"tree",
        password:"gnuern5",email:"vgdg1@yahoo.com"
        expect(molder.errors[:username]).to_not be_empty
        end
```

in account.rb
```
class Account < ApplicationRecord
    validates :username, :password, :email, presence: true
    validates :username, length { minimum: 5 }
    validates :username, uniqueness: true
end
```

As a developer, I need each password to be at least 6 characters long.

in spec/models/account_spec.rb
```
    it 'password must be at least 6 characters long' do
        scully = Account.create username:"grouch123",
        password:"123",email:"vgdg@yahoo.com"
        expect(molder.errors[:username]).to_not be_empty
        end
```

in account.rb
```
class Account < ApplicationRecord
    validates :username, :password, :email, presence: true
    validates :username, length { minimum: 5 }
    validates :password, length { minimum: 6 }
    validates :username, uniqueness: true
end
```

As a developer, I need each password to be unique.

in spec/models/account_spec.rb
```
    it 'password must be unique' do
        scully = Account.create username:"misses tree",
        password:"thetruthisoutthere",email:"vgdg@yahoo.com";
        molder = Account.create username:"mr tree",
        password:"thetruthisoutthere",email:"vgdg1@yahoo.com"
        expect(molder.errors[:username]).to_not be_empty
        end
```

in account.rb
```
class Account < ApplicationRecord
    validates :username, :password, :email, presence: true
    validates :username, length { minimum: 5 }
    validates :password, length { minimum: 6 }
    validates :username, :password, uniqueness: true
end
```

As a developer, I want my Account model to have many associated Addresses.


As a developer, I want Address to have street_number, street_name, city, state, and zip attributes. The street_number and zip should be integers.


As a developer, I want to validate the presence of all fields on Address.

