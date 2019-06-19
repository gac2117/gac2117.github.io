---
layout: post
title:      "Rails with JavaScript Portfolio Project"
date:       2019-06-19 19:54:11 +0000
permalink:  rails_with_javascript_portfolio_project
---

I was very excited to start the JavaScript unit because I knew how popular and crucial JS was in web development. Having a Ruby/Rails background was super helpful because a lot of the concepts and syntax were similar, like conditional statements, methods, and classes. I was able to quickly learn and apply JS through the labs. But the downside to that was going through the curriculum too hastily and not fully practicing writing JS code. 

And towards the end of the unit, the labs had a lot of technical issues and new concepts, like jQuery and API, were not explained in detail. But that led to me looking them up myself and trying to learn through other venues, like YouTube tutorials (Traversy Media is awesome). It does frustrate me when I have to do this, but I'm trying to be optimistic and see it as an opportunity to gain problem-solving/troubleshooting skills.

## Project Requirements
This project was simply adding JavaScript to my existing previous Rails project. That meant I didn't have to brainstorm a new idea for an app, which was fantastic! 

My portfolio project included the following components:
* Had a Rails Backend and new requirements were implemented through JavaScript only.
* Made use of ES6 features as much as possible (e.g. `Arrow Functions`, `let` & `const` variables, `Constructor Functions`)
* Translated the JSON responses into JavaScript Model Objects using ES6 class syntax. 
* Rendered at least one index page via JavaScript and an Active Model Serialization JSON Backend.
* Rendered at least one show page via JavaScript and an Active Model Serialization JSON Backend.
* Included at least one `has-many` relationship through JSON that was then rendered to the page.
* Used my Rails application to render a form for creating a resource that was submitted dynamically and displayed through JavaScript and JSON without a page refresh.
* At least one of the JS Model Objects had a method on the prototype.

## Getting Started
Since I didn't have to create a whole new app, I opened my previous Rails app and tidied up the code a bit. Then I looked at the project requirements, but it was hard for me to understand how implementing those requirements would improve my app. It seemed redundant and useless. Why would I need to show the information on the same page instead of just going to the page itself? But nevertheless, if that's what was required, I had to get it done. So, I started by making a serializer, rendering pages to show JSON responses, creating JS classes, etc. But I still didn't understand how it all connected. So, then my app became cluttered with half-finished JS code.

I decided to attend Office Hours for the project and received two really helpful resources! One was a "Rails - jQuery Office Hours' video and the other was "Rails JS Project - Form Submission Example" video, both by Flatiron School. I watched the video and tried to code along but then nothing was working! Thankfully, I had a project planning call coming up, and that's when I realized **the purpose of this project**!

The project wasn't implementing JS to improve my existing project. *It was to simply practice rending pages using JS and JSON without a page refresh.* That's why the project requirements weren't making sense to me. But after realizing the purpose of the project, I was able to fearlessly make changes without worrying about my Rails project's functionality and efficiency.

## Challenges
First of all, I had created my Rails project app with the hopes of one day perfecting it in order to go live. So, I didn't want to mess up my app with this temporary JS addition. So, I duplicated my repo on GitHub and made a new repo just for this project.

I watched the "Rails - jQuery Office Hours" video twice trying to code along and make my app work. Because my app was more complex than the video's simple example app, I had to change what he was doing in the video to fit my app. That was a challenge in itself, but I learned so much through it. I paused the video frequently to try to implement the codes, figure out why it wasn't working in my app, look up more resources on how I can make it work, and repeat. The video itself is an hour long, but I probably took all day coding along to it. 

One specific challenge I remember was trying to format the date and time! I created constructor functions, used `.toDateString()`, played around in my console, all trying to figure out how to display the date and time correctly on the page. All of the resources I found online were more complex than I wanted to believe. So, I attended another Project Office Hours session and with the coach we were able to figure it out. Turns out, it really is that complicated!

## Conclusion
I realize this every time, but I learn the most through these portfolio projects. I am forced to wrestle with my own codes and refactor them until it does what I want it to do. There's no way I can give up because it needs to work in the end! And because there are no tests to pass, I am able to focus on the actual functionality and execution of my app.

And as always, I am terrified of the project reviews and especially of the live coding exercises. Again, I recognize how important it is for me to do this well, so I welcome the challenge. I just hope I don't get too nervous and perform below my actual ability.

