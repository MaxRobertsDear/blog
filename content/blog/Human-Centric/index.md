---
title: Human-Centric Design
date: "2019-06-15T22:12:03.284Z"
description: Keeping the user at the centre of design
---

#### Over-designing
With so many technologies available, it can be easy to get carried away and use technologies that are simply unnecessary. 
  
Over-engineering has its costs:
* Time - takes longer to build
* Clunky - may impede performance of app if technologies are used unecessarily
* Maintainability - adding technologies can make it more difficult to navigate your code, thereby impeding maintainability

As such, for my final group project at Makers Academy, I set out to tackle the project my asking myself (and prompting my team mates) these questions, in order:
* WHY is there a need for this program? What problems does it solve?
* WHAT will the solution look like? 
* HOW will we solve the problem? What resources can we use to build a solution?

#### Human Centred Design (Why?)
When solving a problem, it seems logical to first think about how an app may be used. *Then* think about which tech stack would be appropriate to build the solution.  

This approach is the one I pushed for during my final group project at Makers Academy.  
  
Wanted the app to be:  
* a service to empower people to 'seize the day'
* simple and easy to use
* lightweight
* simple to build (developer-centric in this instance) so that we could build all the features that we set out to (we had only 7 days to build the app)
* available on the most appropriate device - will the user access the app on their smartphone or their laptop?
* cross-platform - targeting as wide a user-base as possible

#### [x] Human Centred-Design (What?)
[JARVIS](https://github.com/MaxRobertsDear/Jarvis-App), a personal assistant that will create a daily report using your calendar events, live weather / temperature based on your location. The app also greets you with your personalised name and work destination. The daily report can be read aloud to the user, allowing for a convenient hands-free alternative to switching between multiple apps for the same data. This app was produced as our final engineering project at Makers Academy within a timeframe of 9 days.

#### Tech Stack (How?)
* React (cross-platform and JS library so easier to pick up than SWIFT or Kotlin - normally would pick the most appropriate tool for the job, however time limitation was a big decision-making factor)
* Light-weight on the back-end. rather than saving info to a db on a server, thereby making user's data vulnerable to hacking, we decided to store data locally. This was also inspired by similar apps (Citymapper, Weather apps) that do not require user sign up.
* 3rd party code - we sought to use third party code as much as possible. If a required feature already exists and is available to use in your project, it's advantageous to use the third party feature rather than building it yourself: saves on development time and will  already have been tested. 


