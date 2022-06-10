```
$ rails new rolodex_challenge -d postgresql -T
$ rails db:create
$ rails server
```
Open localhost.3000

```
$ rails generate model Person first_name:string last_name:string phone:string
$ rails db:migrate
$ rails c
```

```
$ Person.create

$ Person.create first_name: 'Austin', last_name: 'Walker', phone: '341-235-1234'

$ Person.create first_name: 'Johnny', last_name: 'Depp', phone: '987-654-3120'

$ Person.create first_name: 'Jessica', last_name: 'Depp', phone: '123-423-2344'

$ Person.create first_name: 'Dan', last_name: 'Depp', phone: '987-345-1234'

$ Person.create first_name: 'Henry', last_name: 'Depp', phone: '123-456-8974'

$ Person.create first_name: 'Logan', last_name: 'Ramos', phone: '628-123-9872'
```

```
$ Person.all

$ Person.where last_name: 'Depp'

$ last_person = Person.last

$ last_person.phone = '999-999-9999'

$ last_person.save

$ third_person = Person.third

$ third_person.first_name
```

Stretch
```
$ depps = Person.where last_name: 'Depp'

$ depps.update phone: '777-777-7777'
```