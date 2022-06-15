Setup
Create a new Rails application called 'favorite_movies'.
In desktop
rails new favorite_movies -d postgresql -T
cd into favorite_movies

Create the database
rails db:create

Generate a Movie model with a title attribute and a category attribute
rails generate model Movie title:string category:string
rails db:migrate
code . - open text editor

command T open new terminal
rails c - go to rails

Challenges
Add five entries to the database via the Rails console
Movie.create title: "Spider Man", category: "action"
Movie.create title: "Top Gun", category: "action"
Movie.create title: "Shrek", category: "comedy"
Movie.create title: "Misses Doubt Fire", category: "comedy"
Movie.create title: "Beetlejuice", category: "comedy"


exit rails console, go to favorite_movie repo
Create a migration to add a new column to the database called movie_length
rails generate migration add_column_movie_length

Update the values of the five existing attributes to include a movie_length value


Generate a migration to rename the column 'category' to 'genre'
