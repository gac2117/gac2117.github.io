---
layout: post
title:      "Rails Portfolio Project"
date:       2019-05-27 10:53:46 -0400
permalink:  rails_portfolio_project
---


The portfolio projects are definitely getting harder as they go. But it's also exciting because I am using a lot of the knowledge I've gained through Ruby, HTML, CSS, etc... It's comprehensive, which makes it fun but also challenging. I tried to write notes and write blog posts as I went through the Rails unit because I knew I would need all of this info later on when I do my project. They definitely came in handy and I'll probably continue doing this for my own sake.

## Brainstorming
For this portfolio project, I wanted to make it as realistic as possible (similar to how I approached my Sinatra project). Recently my sister got married and a friend of ours did our wedding makeup. She works as a makeup artist as a side job, and so I thought making an app that helped her clients make appointments would be a good idea for this project. As of now, I've made it simple (just enough to fulfill the requirements of this project), but I hope to continue to work on it as I gain new skills so that she can eventually use it in real life.

This project was a complete Ruby on Rails app that managed data through complex forms and RESTful routes. The users will be able to sign up, sign in, and sign out securely. They would be able to view the makeup artists' profiles and schedule appointments. They can view, edit, and delete their own appointments. The makeup artists will be able to view their upcoming appointments, but not create, edit, or delete them. They can also view the clients' profile pages.

## Project Requirements
My portfolio project included the following components:
- Used Ruby on Rails for the project
- Included two `has_many` relationships (Clients and Artists have many Appointments)
- Included two `belongs_to` relationships (Appointment belongs to Client and Artist)
- Included two `has_many through` relationships (Artist has many Clients through Appointments, and Client has many Artists through Appointments)
- Include at least one `many-to-many` relationship (Artist has many Clients through Appointments, and Client has many Artists through Appointments)
- The "through" part of the has_many through (Appointments) includes three user submittable attributes: `date and time`, `type of service`, and `comments`.
- Included reasonable validations, like `presence` and `uniqueness`.
- Included a class level ActiveRecord scope method (`Appointment.by_date` URL: /clients/1)
- Included signup (`Bcrypt`)
- Included login (`Bcrypt`)
- Included logout (`Bcrypt`)
- Included third party signup/login (`Facebook/OmniAuth`)
- Included nested resource `show` or `index` view (URL: /artists/1/appointments)
- Included nested resource `new` form (URL: /clients/1/appointments/new)
- Included form display of validation errors (form URL: /clients/new)

## Getting Started
Honestly, I was not confident at all going into this project. I didn't feel like I had a strong enough understanding of Rails and I struggled through the last few labs in this unit. So, I started by simply sketching out what my user flow would look like. I jotted down my thoughts on a Word doc and that actually became my main foundation on which I built my app. So, I learned that I don't need to be all organized and perfect from the beginning. Just jotting down my ideas and flow is good enough to get started.

## Challenges
I had some serious challenges as I worked on this project. Just getting the sign up, sign in, and sign out functions to work properly took a day in itself. But then trying to add a third-party signup beat me. The lab on OmniAuth wasn't updated and hard to follow. I think other students also had a hard time with it, so I know I wasn't alone in this. But either way, I had to incorporate it into my app! So, I did a lot of reading and Googling to figure it out on my own. I couldn't get the `thin` server to work, even with the help of a tech coach, and so I ended up deleting the Learn IDE and setting up a local environment as a last resort. I don't know how I managed to do it, but somehow just using `rails s` worked in testing out the Facebook login, so I was satisfied. But then trying to get the user to be able to sign up either using email OR Facebook was another challenge. Watching the lecture video on "OmniAuth Review" helped a lot.

Another challenge was trying to make my app visually appealing. It was during this challenge that I figured out I'm more of a back-end person than a front-end (haha). Again, I went back to reading up on Bootstrap, CSS, etc... all because I wanted to put in a simple navigation bar on top. Not only that, but I wanted the navigation bar to show different menu options for when a user is logged in and not. It took a lot of research, but I was able to incorporate it into my app.

## Solutions
I think I was very frustrated throughout this whole project. I was frustrated at myself and my limited abilities. I was frustrated at the curriculum. I was frustrated at Google (haha). I wished that I had all of this knowledge in my head already instead of having to search for codes and solutions. But then I realized this was probably the best way to learn. I was able to discern what is a good reliable resource and what wasn't. I was able to find good YouTube channels that clearly explained the concepts. And in the end, I was able to finish the project in 5 days.

A new Flatiron resource I used this time was the study groups. I tried joining study groups before, but I couldn't get used to it. I preferred just asking a tech coach or asking on Slack. But this time around, I joined a few study groups and they were all great learning experiences. I was able to get help from the tech coach leading it as well as the other students. I was also able to watch them fix other people's codes and learned from that. I realized how useful and productive the study groups can be.

## Conclusion
Although my app is finished (to the best of my ability), I'm still nervous about the project review. I do learn a lot through the project reviews, but through it I realized that my greatest weakness was my inability to explain code. So, although I am proud of myself for creating this app from scratch, I still don't feel confident enough in explaining it correctly or being able to refactor on the spot. I think I'm pretty slow and I need time to process and write out the code, so doing it on the spot it scary. Therefore, I'm quite intimidated by the project reviews, but since this is something I'm going to have to overcome for future technical interviews, bring it on!
