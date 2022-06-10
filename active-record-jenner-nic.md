Favorite Movies Challenge
Setup
Create a new Rails application called 'favorite_movies'.

```
$ rails new active_record_migration -d postgresql -T
```

Create the database

```
$rails db:create
```

Generate a Movie model with a title attribute and a category attribute

```
$ rails generate model Movie title:string catagory:string
```

Challenges
Add five entries to the database via the Rails console

```
Movie.create title:'Scream', catagory:'Horror'
```

Create a migration to add a new column to the database called movie_length

```
$rails generate migration add_movie_length_to_movie

add_column :movies, :movie_length, :string

$rails db:migrate
```

Update the values of the five existing attributes to include a movie_length value

```
Movie.update_all(movie_length:'100min')

```

Generate a migration to rename the column 'category' to 'genre'

```
$rails generate migration change_name_of_category_to_genre

rename_column :movies, :catagory, :genre

$rails db:migrate
```
