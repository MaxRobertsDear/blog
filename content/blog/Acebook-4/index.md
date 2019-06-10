---
title: First Group Project - Day 4 Reflections
date: "2019-05-23T22:12:03.284Z"
description: Adding DBs & the difference between prototype and MVP
---

### Week 1, Thursday, Morning, Stand up
Confirmed we would work on the tickets chosen during Wednesday’s retro:
* Finish styling.
* Implement databases.
* Progress with the project setup: add a linter, display test coverage and display associated badges on the project README.
  
In this morning’s stand up, we were joined by one of the coaches. Acting as our client, she expressed that she would like to see her username displayed on the landing and posts pages.

### Reflections
Together with the coach we discussed our development approach and our MVP decisions. We learned that there is a distinction between prototyping and working toward MVP. 

MVP is a product that you could take to market. Prototype is used to give the client (and developer) a feel for the look and flow of the app. 

We realised that we were in fact working towards a prototype rather than an MVP. 

Given that in industry, a team might typically have a couple of weeks to build an MVP and we only had a couple of days (working with a new language), the coach was still happy with our decision and encouraged us to stick to plan. She was particularly pleased with our decision to let the front-end guide the back-end. 

---

### Week 1, Thursday, Afternoon, Stand Up
This morning went well. The CSS has been refactored for easier scaling. The setup is almost complete - need to allocate a further 30 minutes to tie up loose ends. 

Time plan for the rest of the day: 
* both teams continue with the morning’s exercise and reconvene after 30 minutes. 
* For the rest of the day: implement the C of CRUD so that the client is able to create a new user and create a post. 

### Reflections
The team working on styling realised the importance of naming html elements appropriately for the sake of scaling. Correctly following CSS’s class and id naming convention makes for easier styling.
  
The group working on set up needed to constantly ask the creator of the project repository on GitHub to accept third parties apps. 
  
Implementing the C of CRUD would satisfy the feedback from the coach in achieving an MVP (thus far, we have only created a prototype).

---

### Retrospective
Yet another productive day. It was realised that the time taken for project set up is not mirrored in the feeling of accomplishment. That is to say, that the team working on the additional set up of the project did not feel that they had much to show for their work, despite working reasonably effectively (when benchmarked against the other teams, who had yet to integrate the additional project set up). 
  
The team working on styling enjoyed working with Max’s code, who had spent his own time on Wednesday evening building a basic template for the styling of the landing page. They found it interesting to work on someone else’s code.  It was easy to read and therefore easy to build upon.
  
Mobbing as a group of 6 is challenging. With so many opinions, it’s easy to get distracted. It’s also important to ensure a steady pace such that everyone has time to understand the current stop before progressing onwards. 
  
Rails does a really good job setting up the file structure. However, because so much is being done for us by Rails, we are sometimes struggling to understand what’s going on ‘under the hood’. We would like to understand how the three databases we currently have (Test, Development and Production) are set up.