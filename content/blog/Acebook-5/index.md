---
title: First Group Project - Day 5 Reflections
date: "2019-05-24T22:12:03.284Z"
description: Experimenting with Devise, a Rails library that handles user authentication
---

### Week 1, Friday, Morning
In the morning stand up we concluded that linking the Users database to its corresponding form would be a priority, as well as aiming towards:
* Attaching and displaying username with a post
* Existing users are able to log in
* Raises errors if sign in details are incorrect, redirecting the user to sign up if they do not have an account already
* Styling fixes (correcting background image on homepage, add a log out button)
However, we also believed it to be in our interest not just to implement, but to also understand the database environment.

### Reflections
The aim of the morning’s tasks was to deepen our understanding of a database’s interaction with rails, travis, and heroku and to successfully link the Users database to the ‘sign in’ html form. 

---

### Week 1, Friday, Afternoon
During the afternoon we decided to continue to integrate Devise, a built-in Rails authenticator, into our project (specifically linking create an account to the database and linking sessions to the log in function). We chose to mob for the integration of Devise on account of the whole team wanting to understand how it works and based on the assumption that we would work faster with 6 rather than a team of 3. Time-boxing the first hour to monitor our progress and reflect on whether to continue as a team of 6 or whether we would be more effective splitting off into smaller groups. 

### Reflections
Understanding how rails handles different environments and databases:
* The development environment is on your computer, and is visible when you run rails server. Running rails db in the command line accesses the development database.
* The production database is separate (can be connected to by cloning the appropriate heroku repository). It is handled entirely by heroku.
* The test environment is only interacted with when using RSpec or directly looking into the test database via PSQL. RSpec-helper updates migrations every time RSpec is run, which in turn updates the test environment.   

Overall, the test and production environments are not typically manually altered.

**Experimenting with Devise:**  
Devise is a rack-based engine that allows for easier authentication of users.

Resources used to set-up and research Devise: set-up guide

Implementing devise took longer than expected, due to a few issues experienced:
* Unable to add devise to existing tables.
* Could recognise existing tables however running migrations threw ‘duplicate name' error.
* Had to remove previously created table and recreate it using devise methods (rails generate devise User).  

A main takeaway from this has been to research potential add-ons in advance as it can avoid time-consuming issues later on (such as having to recreate tables and deleting previously generated files).

---

### Retrospective
The beginning of the mobbing was successful, however once we entered more unfamiliar territory it became too difficult for everyone to follow along. 

We have since decided it is a good idea to stop mobbing when the navigators can no longer clearly navigate due to disagreements on how to proceed or confusion with instructions. When this stage is reached we should instead split off to focus our learning. 

Furthermore, we have emphasised the importance of continuing to share our findings as we have consistently done so throughout our reflections.

We also collectively made our way through a team assessment form, analysing whether we have met the course objectives. When we reconvene, we will correct any requirements not met, including:
* Adding instructions on how to contribute to project in README.
* Adding instructions on how to deploy app in README.
* Adding a link to the wiki in README, citing it as the documentation of our project's journey.
* Discussing and practicing the request / response cycles within our project.