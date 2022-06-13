Validations Challenges
Create a Rails application called company_contacts. The app will have a PostgreSQL database.
Generate a model called Account that has a username, a password, and an email.
All stories should have accompanying model specs.
Developer Stories

As a developer, I need username, password, and email to be required.

```
it 'it will throw an error if username is not true' do
  user1 = Account.create username:nil, password:'mysterydude27', email:'johndoe@gmail.com'
    expect(user1.errors[:username]).to_not be_empty
  end

  it 'it will throw an error if password is not true' do
    user1 = Account.create username:'johndoe77', password:nil, email:'johndoe@gmail.com'
      expect(user1.errors[:password]).to_not be_empty
    end

  it 'it will throw an error if email is not true' do
    user1 = Account.create username:'johndoe77', password:'mysterydude27', email:nil
      expect(user1.errors[:email]).to_not be_empty
    end

     validates :username, :password, :email, presence: true
```

As a developer, I need every username to be at least 5 characters long.

```
it 'it will throw an error if username is less than 5 characters' do
    user1 = Account.create username:'john', password:'mysterydude27', email:'johndoe@gmail.com'
      expect(user1.errors[:username]).to_not be_empty
    end

     validates :username, length: {minimum: 5}
```

As a developer, I need each username to be unique.
```
it 'it will throw an error if username is not unique' do
          Account.create username:'johndoe77', password:'mysterydude27', email:'johndoe@gmail.com'
          user1 = Account.create username:'johndoe77', password:'mysterydude27', email:'johndoe@gmail.com'
            expect(user1.errors[:username]).to_not be_empty
          end
          validates :username, uniqueness: true
```
As a developer, I need each password to be at least 6 characters long.

```
it 'it will throw an error if password is less than 6 characters' do
            user1 = Account.create username:'johndoe77', password:'five', email:'johndoe@gmail.com'
              expect(user1.errors[:password]).to_not be_empty
end
validates :password, length:{minimum: 6}
```
As a developer, I need each password to be unique.
```
it 'it will throw an error if password is not unique' do
              Account.create username:'johndoe7', password:'mysterydude27', email:'johndoe@gmail.com'
              user1 = Account.create username:'johndoe77', password:'mysterydude27', email:'johndoe@gmail.com'
                expect(user1.errors[:password]).to_not be_empty
              end
              validates :username, :password, uniqueness: true
```
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

```

```
