---
layout: post
title:      "Sinatra Project"
date:       2019-04-10 22:26:46 +0000
permalink:  sinatra_project
---


Starting this project was easier than starting my previous Ruby Project. Studying full-time definitely made a big difference! I finished the entire Sinatra Section, which included SQL, ORMs and ActiveRecord, HTML and CSS, and of course Sinatra, in just four weeks. Not only did I make good progress in terms of speed, but I was able to retain the information and comprehend it well enough to do the labs comfortably. Therefore, I was able to approach this portfolio project with a little more confidence than before.
# Brainstorming
For this portfolio project, I was creating a CRUD, MVC app using Sinatra. Basically, it was a small Content Management System (CMS) to keep track of something. I started to brainstorm on what I could make this project about. I wanted to do something more realistic and practical than my last project. I thought of keeping track of all the countries I've been to. I thought maybe I can keep track of my Bible reading plan. But then I remembered how I've been trying to be more physically active (especially since I was sitting in front of my MacBook studying 6-8 hours a day). So, I decided on making a small app that will keep track of what exercise I did in a given day.
# Project Requirements
My portfolio project included the following components:

* Used Sinatra to build the app
* Used ActiveRecord for storing information in a database
* Included one `User` model and one `Exercise` model
* Included one `has_many` relationship on my `User` model (User `has_many` exercises)
* Included one `belongs_to` relationship on my `Exercise` model (Exercise `belongs_to` User)
* Included user accounts with unique login attribute (username). Used ActiveRecord validation helper `uniqueness` to ensure that the username and email address has not been used before
* Ensured that the `belongs_to` resource (exercise) has routes for Creating, Reading, Updating and Destroying
* Ensured that users can't modify content created by other users by comparing the user id of the currently logged in user with the user id of the record they are trying to modify
* Included user input validations for creating a new user and exercise record to make sure no fields are left blank
* BONUS - not required - Displayed validation failures to user with error message using `Rack Flash`
* My README.md includes a short description, install instructions, a contributor’s guide and a link to the license for my code

# Getting Started
I had just finished a major lab, "Fwitter", that was very comprehensive, so everything was fresh on my mind. I decided to tackle the project before my project planning call with the technical coach. I was going to just get the skeleton down and fill it with codes later. 

As always, sitting in front of a blank terminal screen was the most daunting part of getting started. I wasn't sure how to get started because this was different from creating a Ruby gem file. I googled around and watched part of a lecture video to kind of grasp the beginning stages. I made a new repository on Github and tried to sketch out the file structure.

Because this was an app that involved multiple webpages that were all linked together, I found it easier to code once I mapped out how I wanted the webpages to flow. 

1. First, there was the main homepage that will welcome the user. From there, the user can sign up for a new account or log into their already existing account.
2. If they were signing up for a new account, they would need to create a username and password that is unique. If they were logging into their existing account, they would need to provide their username and password correctly.
3. After making a new account, the new user will be directed to creating a new exercise record right away. The user would need to submit the date, the name, and the duration of the exercise.
4. After logging into the existing account, the user will be directed to a list of their own exercise records organized by date. From there, the user can view a single exercise account in order to edit or delete it. Or the user can create a new exercise record. There would also be an option to log out.
5. Finally there would be a page that will show all of the exercise records for the current day for all users.

# Don't reinvent the wheel
In order to start coding, I looked back at my old labs to find codes that were similar to what I'm trying to accomplish right now. 
I fleshed out the file structure to something like this:

```
├── app
│   ├── controllers
│   │   ├── application_controller.rb
│   │   ├── exercises_controller.rb
│   │   └── users_controller.rb
│   ├── models
│   │   ├── exercise.rb
│   │   └── user.rb
│   └── views
│       ├── index.erb
│       ├── layout.erb
│       ├── exercise
│       │   ├── new.erb
│       │   ├── edit.erb
│       │   ├── show.erb
│       │   └── index.erb
│       └── users
│           ├── new.erb
│           └── login.erb
│           └── show.erb
├── config
│   └── environment.rb
├── config.ru
├── db
│   ├── migrate
│   │   ├── 01_create_users.rb
│   │   └── 02_create_exercises.rb
│   └── schema.rb
└
```

Besides these, I had a README file, Gemfile, etc... 

I used the codes and basic flow of logic from previous labs, and then I started to implement my own logic and structure. As I tested out the webpages using `shotgun`, I discovered errors here and there, as well as dead ends. I tried to make the pages flow smoothly without any more dead ends and try to use it like a real user would.

# Extra touches
First of all, I knew I wanted to use helper methods to keep track of the log in status of the user. 
I also thought about using `slug` but realized there wasn't really a reason to because the username is usually one word anyway. 
But I did decide to challenge myself with the bonus requirement of using `Rack Flash` error messages. 
And finally, I wanted to incorporate a little more HTML styling to make the page visually appealing.

As I started to code, everything went very smoothly, and I finished more than I expected on my first day! I actually completed the whole app and it all flowed logically well (in my eyes, at least).
So, the next day, during my project planning call with the technical coach, I showed her what had I finished, and she gave me a few pointers of what I missed, like validations and preventing users from editing or deleting records that weren't their own.

So, on my second day, I started working on those details and went on Slack to ask questions whenever I got stuck.
I also recorded my 30-minute coding session and wrote this blog post.

I didn't want to spend too much time using CSS, so I just used simple HTML to change some colors and fonts. I also added tables so the user can view multiple exercise records more clearly. 

# Conclusion
I'm actually very nervous about finishing so quickly. I feel like I must've missed some requirement or didn't test my app enough. But overall, I'm very happy with what I've made and I'm actually looking forward to the project review with a technical coach. Going through the project review is always a great learning experience, so I hope to continue to learn throughout this whole process!
