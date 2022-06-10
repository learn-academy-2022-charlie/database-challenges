Create a new app called favorite_movies:
rails new favorite_movies -d postgresql -T 

Get into the folder: 
cd favorite_movies  

Create a database:
rails db:create 
// Created database 'favorite_movies_development'
// Created database 'favorite_movies_test'

Create a model: 
rails generate model Movie title:string category:string    
// invoke  active_record
      create    db/migrate/20220610181849_create_movies.rb
      create    app/models/movie.rb


rails db:migrate 
// == 20220610181849 CreateMovies: migrating =====================================
// -- create_table(:movies)
// -> 0.0122s
// == 20220610181849 CreateMovies: migrated (0.0124s) ============================

Movie.create title: "Old", category:"Thriller" 
  TRANSACTION (0.2ms)  BEGIN
  Movie Create (4.4ms)  INSERT INTO "movies" ("title", "category", "created_at", "updated_at") VALUES ($1, $2, $3, $4) RETURNING "id"  [["title", "Old"], ["category", "Thriller"], ["created_at", "2022-06-10 18:33:44.151214"], ["updated_at", "2022-06-10 18:33:44.151214"]]                              
  TRANSACTION (5.2ms)  COMMIT                                
 =>                                                          
#<Movie:0x00007f8a9b1dca40                                   
 id: 1,                                                      
 title: "Old",                                               
 category: "Thriller",                                       
 created_at: Fri, 10 Jun 2022 18:33:44.151214000 UTC +00:00, 
 updated_at: Fri, 10 Jun 2022 18:33:44.151214000 UTC +00:00> 

 rails generate migration add_column_to_movie
      invoke  active_record
      create    db/migrate/20220610183936_add_column_to_movie.rb


Updated movie_length for all movies
```ruby
Movie.all
    Movie Load (0.7ms)  SELECT "movies".* FROM "movies"
    =>                                                                         
    [#<Movie:0x00007f8a9a696258                                                 
    id: 1,                                                                    
    title: "Old",                                                             
    category: "Thriller",                                                     
    created_at: Fri, 10 Jun 2022 18:33:44.151214000 UTC +00:00,               
    updated_at: Fri, 10 Jun 2022 18:52:11.826820000 UTC +00:00,               
    movie_length: 108>,                                                       
    #<Movie:0x00007f8a9a696190                                                 
    id: 2,                                                                    
    title: "Pineapple Express",                                               
    category: "Documentary",                                   
    created_at: Fri, 10 Jun 2022 18:34:58.196680000 UTC +00:00,
    updated_at: Fri, 10 Jun 2022 18:53:24.609932000 UTC +00:00,
    movie_length: 105>,
    #<Movie:0x00007f8a9a6960a0
    id: 3,
    title: "The Interview",
    category: "Documentary",
    created_at: Fri, 10 Jun 2022 18:35:14.826395000 UTC +00:00,
    updated_at: Fri, 10 Jun 2022 18:54:06.265925000 UTC +00:00,
    movie_length: 112>,
    #<Movie:0x00007f8a9a695fd8
    id: 4,
    title: "Starship Trooper",
    category: "Musical",
    created_at: Fri, 10 Jun 2022 18:36:28.178408000 UTC +00:00,
    updated_at: Fri, 10 Jun 2022 18:54:48.640307000 UTC +00:00,
    movie_length: 129>,
    #<Movie:0x00007f8a9a695f10
    id: 5,
    title: "The Batman",
    category: "Political Satire",
    created_at: Fri, 10 Jun 2022 18:37:15.497017000 UTC +00:00,
    updated_at: Fri, 10 Jun 2022 18:55:23.735692000 UTC +00:00,
    movie_length: 176>]

```



rails g migration change_column_category_to_genre
      invoke  active_record
      create    db/migrate/20220610185908_change_column_category_to_genre.rb


 rails db:migrate
== 20220610185908 ChangeColumnCategoryToGenre: migrating ======================
-- rename_column(:movies, :category, :genre)
   -> 0.0069s
== 20220610185908 ChangeColumnCategoryToGenre: migrated (0.0071s) =============