---
layout: post
title:      "CRUD with Rails"
date:       2019-04-30 10:14:20 -0400
permalink:  crud_with_rails
---

How to start from scratch using "Post" as an example (or can use `rails g resource Post ...` generator).

### In `app/models`, create a new model file named `post.rb`
```
class Post < ActiveRecord::Base
end
```

### In `db/migrate`, create a new migration file named `01_create_posts.rb`
```
class CreatePosts < ActiveRecord::Migration
  def change
	  create_table :posts do |t|
		  t.string  :title
			t. text     :description
			t.timestamps  null: false
	 end
 end
end
```

Run `rake db:migrate` to create the database.

### In `config/routes.rb`, draw the necessary routes.
```
resources :posts
```

If you want to use only a few routes, you can add what you need, like `only: [:index, :show, :new, :create, :edit, :update]` 

### In `app/controllers`, create a new controller that inherits from the Application Controller and add all of the necessary actions.
```
class PostsController < ApplicationController
  def index
	  @posts = Post.all
	end
	
	def show
	  @post = Post.find(params[:id])
	end
	
	def new
	  @post = Post.new
	end
	
	def create
	  @post = Post.new(post_params)
		if @post.save
		  redirect_to @post
		else
		  render :new
		end
	end
	
	def edit
	  @post = Post.find(params[:id])
	end
	
	def update
	  @post = Post.find(params[:id])
		if @post.update(post_params)
		  redirect_to @post
		else
		  render :edit
		end
	end
	
	def destroy
	  Post.find(params[:id]).destroy
		redirect_to posts_url
	end

private
  def post_params
	  params.require(:post).permit(:title, :description)
	end
	
end
```

### In `views/posts` create the necessary view files
#### **In the index.html.erb**
To view a list of posts, with links to each post's show page and the option to delete:
```
<% @posts.each do |post| %>
  <li><%= link_to post.title, post_path(post) %></li>
	
	<%= link_to "Delete", post, method: :delete, data: { confirm: "Really?" } %>
  
<% end %>
```

#### **In the show.html.erb**
When viewing a single post with a link to its associated object (like category):
```
<h1><%= @post.title %></h1>
<h3>Category: <%= link_to @post.category.name, category_path(@post.category) if @post.category %></h3>
<p><%= @post.description %></p>
```

When viewing a list of posts for one category (similar to the index.html.erb for posts):
```
<h1><%= @category.name %></h1>
<h3><%= pluralize(@category.posts.count, 'Post') %></h3>
<ul>
  <% @category.posts.each do |p| %>
    <li><%= link_to p.title, post_path(p) %></li>
  <% end %>
</ul>
```

#### **In the new.html.erb** using `form_tag` (used when it isn't connected to models, like search engines)
```
<h3>Create Form</h3>
<%= form_tag posts_path do %>
  <label>Post title:</label><br>
  <%= text_field_tag :title %><br>

  <label>Post Description</label><br>
  <%= text_area_tag :description %><br>

  <%= submit_tag "Submit Post" %>
<% end %>
```

#### **In the edit.html.erb** using `form_for`
```
<h3>Post Form</h3>
<%= form_for @post do |f| %>
  <%= f.label 'Post Title' %><br>
  <%= f.text_field :title %><br>
	
  <%= f.label 'Post Description' %><br>
  <%= f.text_area :description %><br>
	
  <%= f.submit "Update Post" %>
<% end %>
```

