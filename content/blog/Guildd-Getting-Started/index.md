---
title: Guildd - Getting Acquainted with my 1st Open Source Project
date: "2019-07-10T23:46:37.121Z"
description: Setting up the environment and why I started working on Guildd
---

### Dipping in my Toe

**Instructions for my first pull request:**

>> Essentially I'd like a declarative approach to writing forms, where the Fields and their Inputs can be described via JSX and errors can be supplied which are then rendered onto the Fields.

Sounds easy, right?

Depends on whether you're familiar with the tech stack. 

Sticking points and technologies that I hadn't come across before:
* Advanced react (such as hooks)
* Libraries such as Formik 
* ES6's destructuring 
* `<Wrapper />`
* Docker
* Lambda-graphql
* Webpack 
and many more. 

### Unfamiliar Territory

Working on a project where I wasn't acquainted with every technology within it was new to me - until now, I helped build all my projects from scratch and so knew exactly which technologies were being used and why. Working on Guildd was different. I was jumping in at a point where the tech stack had been chosen and some basic features had already been implemented. 

### Getting Started - Setting up the Environment

I didn't anticipate spending so much time getting the environment set up. Coming from a background where I had set up all my projects from scratch was distinct from using someone else's code. There was no README with installation instructions (which I decided would be my first order of business) and the originator was unavailable. All I could do was to follow the error prompts on my terminal, using stackoverflow to decrypt any confusing messages - FYI, there were *a lot* of confusing messages.

I shan't bore you with the details, but I updated the README with the following installing instructions:

```bash
yarn install
brew install aws-sam-cli
brew link aws-sam-cli --overwrite --force
brew install watchman
brew install postgis

docker-compose up -d # Run Postgres

createuser --superuser guild
yarn sequelize db:create
yarn sequelize db:migrate

yarn start
yarn relay
yarn dev
```

Open up localhost:8888 in your browser

How to test:

```bash
yarn test
```

### Why Open Source

One of the main reasons for contributing to an open source project was to learn how to collaborate with developers of a higher seniority, observe the way that they code, and to gain industry experience. Plus, the project sounded really fun! I was excited by the prospect of contributing to something that might one day be of value to users. 

---

Check out my next post on how I tackled my first pull request.






