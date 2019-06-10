---
title: First Group Project - Day 3 Reflections
date: "2019-05-22T22:12:03.284Z"
description: CI/CD & sharing credit
---

### Week 1, Wednesday, Morning, Stand up
The morning stand up involved:
1. Recapping what was achieved the previous day to ensure that everyone was up to speed 
2. Reviewing the items in the to-do column of our project board and picking the days priorities
3. Assigning tickets to team members
  
We decided to split off into two teams of three, with the aim to:
* Deploy the site with Heroku (the CD of our CD/CD)
* Add MVP functionality to the sign up and (time permitting) the log in page

### Reflections
It was agreed to prioritise the integration of the CI/CD and we felt optimistic that we achieve this done by the end of the day. The stand up proved beneficial in ensuring that everyone’s understanding of the MVP were mirrored.
  
A point that was raised during the morning session was that we need to be mindful about crediting each other’s contributions. This was especially true in our case, where one person would be driving and the other two navigating. 
  
Accurately reflecting each team member’s contributions also helped us towards one of the course goals of demonstrating an equal distribution of work. This was achieved by using the 'Co-authored-by:' feature on Github during pairing sessions.

---

### Week 1, Wednesday, Afternoon, Stand up
The afternoon catch up gave insight into what had been achieved in the morning:
* The sign up and login routes had been set up, with the assumption that the user would only perform successful actions.
* Spent time understanding how routing works in Rails and the 'syntactic sugar' that comes with the framework e.g adding resources to your app routes.rb file generates RESTful routes that come with pre and controller actions.
* We had our app deployed on Heroku which meant that we were on schedule to be able to send our 'client' a link to a live website.
* Overall, the morning went well with progress towards an MVP being made by both groups.
  
The afternoon’s session was shorter than usual due to a careers workshop . As such, we tried to keep our goals achievable:
* Add styling to the sign up and login pages.
* Fix a bug in the Heroku-Travis integration: Travis builds are failing to deploy despite being deployed in Heroku.

### Reflections
We started modelling the UI before we had finished our stand up but managed to catch ourselves quickly and bring the focus back to planning the rest of the day. 

After the stand up we continued to model the UI as a team to make sure everyone was happy with how the app was going to be styled. 

We also thought that it would be best to continue with the CI/CD configuration to make sure that builds were passing as there was good progress with getting the app deployed in the morning.

---

### Retrospective
Overall, the team had a productive day. Everything that was set out to be achieved had been completed. 
  
Some time was wasted in trying to apply a CSS template that had a tightly coupled HTML template, thereby making it difficult to use. Rather than restructuring the team’s existing HTML file, it was decided that although writing our own CSS will be more time-intensive, that the code-base would look a lot cleaner and would therefore be easier to maintain. 
  
Writing our own CSS also gave our team ownership for all the completed work.
  
What went well:
  
* Fixed the bug with the CI/CD integration which was great - this turned out to be due to redundant code in our Travis configuration file.
* Added styling to our app that can be easily applied to other areas of the app.
* Made good progress towards an MVP which means we might have time to implement the database functionality to support user authentication before the client meeting.  

Key learnings:
* We became aware of the pitfalls of following tutorials and the importance of thinking about what you are trying to achieve and what your code is actually doing.
* Make use of the resources that we have - coaches and other cohort members can help overcome knowledge-hurdles.
* Focus on meeting the minimum requirements.
* Using CSS templates can tie you to a specific way of structuring your HTML and might not always be quicker if you only need to add a minimal amount of styling.
