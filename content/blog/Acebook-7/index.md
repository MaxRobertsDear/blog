---
title: First Group Project - Day 7 Reflections
date: "2019-05-29T22:12:03.284Z"
description: Git workflow deepdive
---


### Week 2, Wednesday Morning
After going over our retro from yesterday, we set out the morning’s goals:

* Complete User Sign Up and Log In routes
* Link the Usernames to Posts
* Fix validation for email and password
* Set up a Devise Branch and DRY up tests
* Transfer style sheets over to new Devise routes

We decided that we would split into three groups of two and each tackle a set of related tasks. Jose and Max would sort out the styling transfer, Ayelisha and Hannah would link the usernames to posts with styling, while Marcus and Xain would DRY up the tests, create a maximum password limit for the sign up and log in forms, and set the landing page to the sign up page.

### Reflections
The standup went smoothly and each team was given a pretty even workload. We had to spend about 40 minutes fixing Travis and ensuring everyone had an updated yml file before we could proceed, but we achieved most of the morning’s goals in spite of that.

---

### Week 2, Wednesday Afternoon
We had a couple of remaining tasks from the morning per pair, so we continued in our pairs on them instead of switching rolls. Specifically, these tasks were:
	•	Create a redirect when a non-signed in user tries to visit the Posts page.
	•	Transfer styling to Devise Views
	•	Create styling for Posts page 

Overall we made significant headway, particularly on the front end of the web app. The routing was essentially sorted, but still needed a bit of tweaking. The styling transfer depended on the routes being fixed, but the pages have been updated on a separate branch. By 5pm, we achieved our day’s goals on separate branches.

---

### Retrospective
The team was productive by the day’s end and each pair was able to demonstrate the changes they made easily and understandably to the rest of the team. Everyone was confident in what we had achieved, but everyone felt that our only issue was that our respective merges would conflict as we all had to edit the tests somewhat. Marcus and Xain agreed that the time spent trying to sort out the root for Devise took long as there were too many conflicting sources of information on how to do it. 

**What went well:**  
* We achieved all of our goals of the day, officially giving us an MVP

**What didn’t go well**  
* We didn’t communicate enough as a team on when pushing and merging needed to happen.
* Some of the research into Devise was time consuming.

**Key learnings:**  
* Decide an approach to pushing and merging when everyone is working on similar files. Whose changes takes precedence? 
* Splitting into teams and distributing work properly in a way that connects each pair’s task to the project as a whole is an effective way to deal with a group of varying User Stories.
* Stack Overflow is a very helpful rabbit hole
* Sorting out Devise from the beginning is imperative for avoiding bugs with TDD and routing.
