## Favorite Movies Challenge
# Setup

- Create a new Rails application called 'favorite_movies'.
> $ rails new app_name -d postgresql -T
$ cd app_name

- Create the database
> $ rails db:create
$ rails server

- Generate a Movie model with a title attribute and a category attribute
> $ rails generate model Movie title:string category:string
 $ rails db:migrate

# Challenges

- Add five entries to the database via the Rails console
> Movie.create title: "Up", category: "Family"
Movie.create title: "True Lies", category: "Action"
Movie.create title: "Spy Game", category: "Action"
Movie.create title: "Titanic", category: "Drama"
Movie.create title: "Toy Story", category: "Kids"

- Create a migration to add a new column to the database called movie_length
> Create a migration file
    > $ rails generate migration add_column_movie_length

> Edit the file
    > db/migrate/...add_column_movie_length.rb
    > def change
    > add_column :movies, :movie_length, :integer

> Merge the migration file
    > $ rails db:migrate


- Update the values of the five existing attributes to include a movie_length value
> entry1 = Movie.find 1
> entry1.movie_length = 75
> entry1.save
> / Repeat for each entry /


- Generate a migration to rename the column 'category' to 'genre'
> $ rails generate migration update_category_to_genre

> Edit the file
    > db/migrate/...update_category_to_genre.rb
    > rename_column :movies, :category, :genre

> Merge the migration file
    > $ rails db:migrate