---
layout: post
title:      "Rails with React-Redux Portfolio Project"
date:       2019-07-25 17:25:21 +0000
permalink:  rails_with_react-redux_portfolio_project
---

I can't believe I'm doing my last portfolio project. The past five months have been quite an adventure since coming back to the States and studying full-time. All the lonely hours spent in my bedroom coding are about to pay off now. Everything comes together in this final project. The React-Redux section of the curriculum looked shorter than the others, but it was full of new terminology and concepts. Again, I couldn't have comprehended everything without the help of outside sources, like Traversy Media YouTube videos and tech blogs, as well as the tech coaches.

## Project Requirements
This project was truly a comprehensive project comprised of a single-page application with a Rails API back-end and a React frontend.

My portfolio project included the following components:
* Built a RESTful JSON API with Rails using `fast JSON API` serializer.
* Included two container components, four stateful components, and 5 stateless functional components.
* Made use of ES6 features as much as possible. 
* Utilized `react-router` and RESTful routing for four routes.
* Incorporated a Redux store to hold the state and Redux middleware to respond to and modify state change. Defined Redux actions for updating the store and Redux reducers to return the new state.
* Used `fetch()` within the Redux actions to `GET` and `POST` data from the Rails API.
* Utilized `reactstrap` to style the views.

## Getting Started
Similar to the JavaScript portfolio project, I had a hard time understanding the project requirements. I usually get started on my project before my project planning call with the tech coach, but this time I just couldn't get started. So instead, I just brainstormed general project ideas. A friend gave me an idea for an app that will allow the user to enter their favorite restaurants and at the click of a button, it will choose one of the restaurants for the user to go eat at. There are many times when a group of friends take forever choosing a restaurant to go to, so this app is for them! It sounded like a useful, realistic idea so I decided to make that app.
 
During my project planning call, my tech coach was able to clarify all of the project requirements. But hearing all of what I had to do was quite overwhelming. First of all, I had no idea I was creating essentially TWO apps: one Rails backend app and one React frontend app. I thought I had to fetch data from an external API source, but it turns out I had to create my own Rails API, which we've never done before. That was daunting to find out.

Thankfully, my tech coach had some resources for me to look at. Another tech coach had recently done a live coding session that covered all of the project requirements, so she gave me those videos to watch. She also gave me some good tech blogs that covered the differences between class and functional components, as well as presentational and container components. With those in hand, I started building my app.

## Challenges
This was by far the most difficult and extensive app I had to make. There were so many challenges and blockers every day that I worked on this app. First, I tried to visualize how I wanted my app pages to look. I drew it by hand and then figured out which containers will hold which components. But then when I tried to code it, my Redux store wasn't being updated or I wasn't passing the props correctly. This was so frustrating, but it helped me to understand what exactly `mapStateToProps` does, how Redux actions and reducers work, how to fetch data from the database and dispatch it to the Redux store, etc... It was a lot of trial and error (and reading tech blogs) but it was a great learning experience.

Another big challenge was implementing the randomizer for choosing a restaurant from the list of restaurants in the Redux store. Thankfully I was able to find bits and pieces of code online that kind of gave me an idea on how I can "randomly" select a restaurants from the store, but again it was such a pain to figure out how to use `componentDidMount()` verses `componentWillMount()` and just the order of functions being called and the state being set. It was exhilarating to finally get it to randomly choose a restaurant from my list!

A personal challenge for me is making my app look visually appealing. I simply do not have the eye for color coordination or a decent layout. So, I decided to incorporate `reactstrap` and make it to the hard work for me. A friend recommended a good color scheme, so I customized the `reactstrap` components with CSS styling to get the colors right. This was towards the end of my project, so I was eager to get it done, but surprisingly this styling took longer than I thought. But again, when it was done, I was very pleased with how everything looked.

I was ready to submit my project, but I wanted to test it out, so I asked a friend to play around with the app "to try to break it". Unfortunately, he was able to find all kinds of bugs and broken functionality, so I was back to coding again. Although it was disappointing to know I wasn't actually done with the project, I'm so glad my friend found those mistakes rather than them being discovered during the project review!

So, after a day of additional coding, I was again ready to submit my project. I started writing this blog and checking my app with the final project checklist. But then I found another (shocking) discovery. My stateless components were class components and not functional components. Also, my container component did render some text although it wasn't supposed to. Basically, in my eagerness to make my app function the way I wanted it to, I disregarded the project requirements I had to fulfill and solely focused on functionality. Granted, these weren't big changes that I had to make, but again it was another delay.

## Conclusion
Finally, after more research on how to pass props to stateless functional components and bugging my tech coach, I am finally REALLY done with my project. All of my previous projects were completed within a week from conception to submission. But this project took me 11 days of nonstop coding. And like every project before this, it is when I am wrestling with my project that I learn the most. I'm so grateful to my patient tech coach and fellow coders on Slack for helping me out whenever I got stuck. Now I only have my project review left and then... GRADUATION!

