Create rails app

``` 
$ rails new favorite_movies -d postgresql -T
$ rails db:create
$ rails generate model Movie title:string category:string
$ rails db:migrate
```

```
$ rails c 
$ Movie.create title: 'John Wick', category: 'Action'
$ Movie.create title: 'Doctor Strange 2', category: 'Action/Adventure'
$ Movie.create title: 'Shrek', category: 'Comedy'
$ Movie.create title: 'Top Gun', category: 'Action'
$ Movie.create title: 'Kung Fu Panda', category: 'Action / Comedy'
```

```
$ rails generate migration add_column_to_movies_named_movie_length
```
Inside migration file
add_column :movies, :movie_length, :integer 
`$ rails db:migrate`

Assigned variables to all movies
first_movie = Movie.first 
etc.

first_movie.movie_length = 2
first_move.save
etc.

all_movies = Movie.all
all_movies.update movie_length: 2


```
$ rails generate migration rename_column_from_category_to_genre
In new migrate file
rename_column :movies, :category, :genre
$ rails db: migrate
```


Setup
Create a new Rails application called 'favorite_movies'.
Create the database
Generate a Movie model with a title attribute and a category attribute
Challenges
Add five entries to the database via the Rails console
Create a migration to add a new column to the database called movie_length
Update the values of the five existing attributes to include a movie_length value
Generate a migration to rename the column 'category' to 'genre'