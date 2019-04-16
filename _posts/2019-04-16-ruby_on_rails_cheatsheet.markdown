---
layout: post
title:      "Ruby on Rails Cheatsheet"
date:       2019-04-16 19:24:34 +0000
permalink:  ruby_on_rails_cheatsheet
---

After going through two portfolio project reviews, I realized my biggest weakness was the technical terminology. I wasn't able to explain my code effectively using the appropriate vocabulary. I thought as long as I understood the concepts and can use what I learned properly, I was good to go. But when the tech coach was asking me about my code or telling me to refactor, I wasn't able to understand what he was asking me to do... That was a huge problem.

So as I started Ruby on Rails, I decided to organize some of the basic concepts and terminology in this blog post for future reference. 

# What is Ruby on Rails?
*  A web framework that provides developers with the tools they need in order to build applications
*  A Ruby gem (a set of Ruby code libraries)
*  A MVC (Model-View-Controller) framework placing the logic for the application in the model files, managing the code flow in the controllers, and displaying content to the user in the views.
*  It is NOT a programming language!

# Creating a new Rails app
To create the application, run the following command: `rails new app-name`

The app name should be lowercase and words should be connected with a hyphen, as above.

# Rails File Structure 
* app – contains the MVC. This is the one directory where you can make a change and not have to restart the Rails server. In addition to the full MVC structure, this directory also contains non Ruby files, such as: css files, javascripts, images, fonts, etc.

* bin – some built-in Rails tasks 

* config – manages the environment settings, a set of modules that are initialized when the application starts, the ability to set language values, the application settings, the database settings, the application routes, and lastly the secret key base.

* db – holds the database schema file that lists the database tables, their columns, and each column’s associated data type. The schema file can be found at db/schema.rb. The db directory also contains the seeds.rb file, which lets you create some data that can be utilized in the application. 

* lib – The lib/tasks directory is where custom rake tasks are created.

* log – holds the application logs. This can be helpful for debugging purposes.

* public – this directory contains some of the custom error pages, such as 404 errors, along with the robots.txt file which will let developers control how search engines index the application on the web.

* test – by default Rails will install the test suite in this directory. This is where all of your specs, factories, test helpers, and test configuration files can be found.

* tmp – this is where the temporary items are stored and is rarely accessed by developers.

* vendor – In Rails 4+, its main purpose is for integrating Client-side MVC frameworks, such as AngularJS.

* Gemfile – the Gemfile contains all of the gems that are included in the application. After any change to the Gemfile, you will need to run `bundle install`. 

* Gemfile.lock – this file should **not** be edited. It displays all of the dependencies that each of the Gems contain along with their associated versions. 

* README.rdoc – the readme file is an important place to document the details of the application. If the application is an open-source project, this is where you can place instructions to other developers, such as how to get the app up and running locally.

# Getting Started
Before starting up the Rails server, create the database by running `rake db:create`.

Start up the Rails server by going into the root directory and running `rails s` in the terminal. (this is like `shotgun` in Sinatra). To shutdown the server, press CTRL+C.

To use the Rails console, run `rails c` to start and press CTRL+D to end. (this is like IRB but with the full Rails environment). 

# Rails MVC
Models - a model is a Ruby class. It will inherit from ActiveRecord::Base

Views - a view file should have the least logic involved. It should only render what is sent from the database. Rails has ActiveView helper methods that can help you synamically set the HTML tags without writing actual HTML code.

Controllers - a controller connects the models, views, and routes. 
# Routing
**Static route** - A static route will render a view that does not change. Typically, you will not send parameters to it. Examples would be a site's "about" or "contact" pages.

**Dynamic route** - Dynamic routes are pages that accept parameters and render different content based on those parameters. For example, `get '/articles/:id' ` will render a different page for whatever `id` is in the URL

*How HTTP works*:
1. A URL is entered into the browser; this is the HTTP request
2. That request is sent to the server where the application's router interprets the request and sends a message to the controller mapped to that route
3. The controller communicates with the view file mapped to the controller method
4. The server returns that HTTP response, which contains the view page that can be viewed in the browser

# Example of Static Route codes
**To draw the route**, go to `config/routes.rb` and add the following route inside the `draw` block:
```
get 'about', to: 'static#about'
``` 

The HTTP verb is `get`

The path is `about` which the route will be mapped to: `/about`

The controller action is `static#about` which tells the routing system that this route should be passed through the `static` controller's `about` action ('action' is a method in a controller). So in `StaticController`, there will be a method called `about` that gets called when the user goes to `/about`

**To create a new controller** for the static pages, add `app/controllers/static_controller.rb` file with this code: 
```
class StaticController < ApplicationController
   def about
	 end
end
```

*Explicit rendering* - Rails lets you dictate which view file you want to have the controller action mapped to.

*Implicit rendering* - Rails follows the standard convention that automatically looks for a view file with the same name as the controller action. This means, if the view file is named `about.html.erb` then there is no need to write `render "about"` to bring up the view.

**To create a new view file**, create a new directory within the views directory called `static` and create a new file called `about.html.erb`. 

# Example of Dynamic Route codes
**To draw the route**, go to `config/routes.rb` and add the following route inside the `draw` block:
```
get 'posts/:id', to: 'posts#show'
``` 
As you can notice, the route `/:id` tells the routing system that this route can receive a parameter and will be passed to the Posts Controller's show action.

**To create a new controller** for the posts pages, add `app/controllers/posts_controller.rb` file with this code: 
```
class PostsController < ApplicationController
   def show
	    @post = Post.find(params[:id])
	 end
end
```

**To create a new view file**, create a new directory within the views directory called `posts` and create a new file called `show.html.erb`. 

# Resource Routing
Instead of the `get` route in the `routes.rb` file, you can use RESTful defaults and the `resources` method. If you only want one of the seven key RESTful routes, then we can use the `only` option.

In the `route.rb` file, you can write:
```
resources :posts, only: :show
```
and it will do the same as the above code.

# Rails URL Helpers
Instead of hard-coding route paths, you can use built-in URL helper methods. That way, if something changes with the route, the code itself may not need to be changed. But these helper methods cannot be used in the model files. 

*Hard coded route paths*: `"/posts/#{@post.id}"`

*Route helper*: `post_path(@post)`

**To implement route helpers**, in the `config/routes.rb` check the route call `resources :posts, only: [:index, :show]`

**To check routes**, run `rake routes` 
```
posts     GET     /posts(.:format)         posts#index
post       GET     /posts/:id(.:format)   posts#show
```
1. `posts` and `post` are prefixes for the route helper methods. The two most popular method types are `_path` and `_url` but using `_path` is recommended because it gives the relative path, like `posts_path`
2. GET is the HTTP verb
3. This is what the path for the route will be and what parameters need to be passed. So if we use the route helper, the `index` route will have a route of `posts_path` but the `show` route will look like `post_path(@post)`.
4. This is the controller and action (method name) -- `controller#action`

**Use the link_to method** to create HTML code `<a href="...">...</a>` 

Instead of writing this long code:
```
<% @posts.each do |post| %>
  <div><a href='<%= "/posts/#{post.id}" %>'><%= post.title %></a></div>
<% end %>
```

Use `link_to` method to get rid of multiple ERB calls:
```
<% @posts.each do |post| %>
  <div><%= link_to post.title, "/posts/#{post.id}" %></div>
<% end %>
```

But this can be improved by using `post_path`:
```
<% @posts.each do |post| %>
  <div><%= link_to post.title, post_path(post) %></div>
<% end %>
```
and no need to write `post_path(post.id)` because Rails already knows this is the ID attribute.

