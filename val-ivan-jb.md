create  a new rails app
```
-rails new validation -d postgresql -T
    -then cd into the app
- Now we bundle by adding rspec
```

```
require 'rails_helper'

RSpec.describe Account, type: :model do
  
    it 'has a username' do

      worker = Account.create password:'password', email:'tiger10@gmail.com'

      expect(worker.errors[:username]).to_not be_empty
    end
    it 'has a password' do 

    worker = Account.create username:'Sully',  email:'tiger10@gmail.com'

    expect(worker.errors[:password]).to_not be_empty
    end
    it 'has a email' do 

      worker = Account.create username:'Sully', password:'password' 
  
      expect(worker.errors[:email]).to_not be_empty
    end

    it 'has 5 or more character in a username' do

      worker = Account.create username:'hel', password:'password', email:'tiger10@gmail.com'
      # p (worker.errors[:username])
      expect(worker.errors[:username]).to_not be_empty
    end
    it 'has unique usernames' do
      Account.create(username:'hell', password:'password', email:'tiger10@gmail.com')
      worker = Account.create(username:'helo', password:'password', email:'tiger10@gmail.com')
      p (worker.errors[:username])
      expect(worker.errors[:username]).to_not be_empty
    end
  
  
end

```
```
class Account < ApplicationRecord
    validates :username, :password, :email, presence: true
    validates :username, length:{minimum: 5}
    # validates :username, uniqueness: true
    # validates :username, uniqueness: { case_sensitive: false }
end

```