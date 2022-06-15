# Migrations with Active Record

```bash
rails new favorite_movies -d postgresql -T
cd favorite_movies
rails db:create
rails generate model Movie title:string category:string
rails db:migrate
rails server
```

Open new Terminal

```bash
rails c
Movie.create title:'Jaws', category:'Thriller'
Movie.create title:'Argo', category:'Action'
Movie.create title:'Batman', category:'Action'
Movie.create title:'13 Ghosts', category:'Scary'
Movie.create title:'Due Date', category:'Comedy'
```

## Migration

In new terminal window

```bash
rails generate migration add_column_move_length
```

Open file created in `db/migrate` that is associated with the migration
Edit change method to enclose the following

```ruby
add_column :movies, :movie_length, :integer
```

Request Migration

```bash
rails db:migrate
``` 

## Add Movie Lengths

Open Rails Console
```bash
rails c
```

```ruby
movie_jaws = Movie.find 1
movie_argo = Movie.find 2
movie_batman = Movie.find 3
movie_13_ghost = Movie.find 4
movie_due_date = Movie.find 5

movie_jaws.movie_length = 160
movie_argo.movie_length = 120
movie_batman.movie_length = 140
movie_13_ghost.movie_length = 120
movie_due_date.movie_length = 91
```
