---
title: Guildd - My First Pull Request
date: "2019-07-10T23:48:37.121Z"
description: My first Open Source Project
---

Having set up the environment, it was time to make a start on my first pull request. 

**Instructions for my first pull request:**

>> Essentially I'd like a declarative approach to writing forms, where the Fields and their Inputs can be described via JSX and errors can be supplied which are then rendered onto the Fields.

### Narrowing my Focus

I could have spent hours learning all of the technologies that were unfamiliar to me on Guildd but didn't feel that that would be the most constructive use of my time. Instead, I narrowed my focus on the technologies that I needed to manipulate in order to complete my first pull request:

* React Context - what is it used for / how does it relate to forms?
* Formik - what is it and why is it used?
* GraphQL - what are mutations?

### Learning <Formik />

1. Read the documentation for <Formik /> and <Form /> (both of which were being used in the project already).
2. Watched video explaining Formik's motivation and philosophy and demo how to build a non-trivial form.
#### Why forms are hard (according to the creator of Formik)
>>* Wiring up state
>>* Validation
>>* Error messages
>>* Staying organized
>>* Testing
>>* Not bashing your face against your keyboard 
3. Manipulated existing code and observed it's effect on the forms page (run with localhost) to understand its function.


#### React Context and how it fits within Formik

1. Read the documentation for React Context
2. 

### Learning GraphQL

https://www.howtographql.com

Understood the use case of GraphQL by contextualising - how does it differ from REST in terms of data fetching and what are the advantages of GraphQL over standard REST.

What is a benefit of the GraphQL schema and strong type system?

Once the schema is defined, frontend and backend teams can work independently from one another. (I guessed this correctly, but I don't know why this answer is the case) ...

Mutations are a way of changing making changes to the data that is stored in the back-end. GraphQL mutations:
* create
* update
* delete

e.g.

mutation {
  createPerson(name: Jon, age: 35){
    id
  }
}

A person with the name Jon and age of 35 is added to the Persons table. An id is automatically generated for each row that is added to the table and this can be retrieved as in the example above. 









