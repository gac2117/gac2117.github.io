---
layout: post
title:      "Intro to MongoDB"
date:       2020-01-16 21:42:53 +0000
permalink:  intro_to_mongodb
---


MongoDB is a noSQL database, which stands for *not only SQL*. These databases store data in collections of documents, like JavaScript objects. MongoDB is very scalable, fast, and flexible. There is no need to map out data structure like relational DB. 

To install on a Mac, go to [mongoDB](https://docs.mongodb.com/manual/tutorial/install-mongodb-on-os-x/#install-mongodb-community-edition) and follow the instructions.  

Basically, if you already have [Homebrew]( https://brew.sh/) set up, then run these commands in the terminal to install MongoDB.
1.	Tap the MongoDB Homebrew Tap:
`brew tap mongodb/brew`
2.	Install MongoDB:
`brew install mongodb-community@4.2` (or whatever the current version is)
3.	Run MongoDB as a MacOS service:
`brew services start mongodb-community@4.2`

In your terminal, type `mongo` to run your mongo shell.

If you want to use Compass, you’ll need to download it separately since Homebrew won’t install it for you. 

## MongoDB commands

`show dbs` will show all the databases.

`use test1` will create a new database called "acme" and go into it. Until you create a collection inside the new database, it will not show up in the list of databases.

`show collections` will show the collections in the database you're currently in.

`db.dropDatabase()` will delete the current database that you’re in.

`db` will check what database you’re in.

## Creating a collection

`db.createCollection(‘posts’)` will create a collection called "posts".

```
db.posts.insert({
   title: ‘Post One’,
   body: ‘Here is post one’,
   category: ‘News”,
   likes: 4,
   tags: [‘news’, ‘events’],
   user: { name: ‘John Smith’, status: ‘author’},
   date: Date()
 })
 ```

This will create a document in the collection “posts” with a title of "Post One" and insert regular strings, numbers, arrays, embedded objects, dates.

To make many documents at once, you can:

```
db.posts.insertMany([
{ title: ‘Post Two’,
   body: ‘Here is post two’,
   category: ‘Technology’,
   date: Date()
},
{ title: ‘Post Three’,
   body: ‘Here is post three’,
  category: ‘News’,
  date: Date()
}, 
{ title: ‘Post Four’,
  body: ‘Here is post four’,
  category: ‘Entertainment’,
  date: Date()
}
])
```

## Query through the collection

> Tip: Adding `.pretty()` at the end of the line will make the results more readable
> 

`db.posts.find()` will query all of the data in the collection “posts”

`db.posts.find({category: ‘News’ })` will query all of the data that has the category of “News”

`db.posts.find().sort({ title: 1})` will query all of the data and sort it by the title. 1 will sort ascending and -1 will sort descending.

`db.posts.find({ category: ‘News’ }).count()` will count how many posts have the category ‘news’

`db.posts.find().limit(2)` will limit the query to the first two posts created

`db.posts.find().forEach(function(x) {print (‘Blog Post: ‘ + x.title) })` will go through the posts and for each one it will print out the words ‘Blog Post:’ and the post title.

`db.posts.findOne({ category: ‘News’ })` will find just one result. In this case, the first post with the category of ‘News’

## Updating a document

> Be careful when you update because you can replace all the contents with what you are entering.
> 

```
db.posts.update(
{ title: ‘Post Two’ },
{ title: “Post Two”,
   body: “New post 2 body”,
   date: Date()
},
{ upsert: true}
)
```

The first parameter is the identifier; in other words, what post you want to update (post with the title "Post Two")

The second parameter is the data you want to update.

The third parameter is optional. "Upsert" means update and insert. So if this document isn’t found, it will create it in the database. 

#### The set operator ($set) will only update the data you specify:

```
db.posts.update(
{ title: ‘Post Two’ },
{ $set: { category: ‘Technology’} }
)
```

This will keep the rest of the data and only update the "category". Doing this is recommended!

#### The increment operator ($inc) will add numbers for you:

```
db.posts.update(
{ title: ‘Post One’}, 
{ $inc: { likes: 2}}
)
```

This will increment the number of likes by 2.

#### The rename operator ($rename) will rename the field:

```
db.posts.update(
{ title: ‘Post One’}, 
{ $rename: { likes: ‘views’}}
)
```

This will rename the field ‘likes’ into ‘views’. 

## Deleting a document

```
db.posts.remove(
{ title: ‘Post Four’}
)
```

This will delete the document with the title "Post Four"

## Subdocuments

#### Embed the subdocuments into the main document:
```
db.posts.update(
{ title: ‘Post One’ },
{ $set: {
    comments: [
       { user: ‘Johnny Appleseed’, body: ‘Comment One’ },
       { user: ‘Jane Doe’, body: ‘Comment Two’ }
    ]
	}}
 )
```
 
This will embed "comments" into "Post One". You can have many comments associated with the post.

#### To query the subdocuments:

```
db.posts.find(
{ comments: {
     $elemMatch: { user: ‘Jane Doe’ }
   }}
)
```
	 
This will query all the comments with the "user" of "Jane Doe". 



