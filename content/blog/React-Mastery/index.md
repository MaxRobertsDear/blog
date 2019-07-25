---
title: Guildd Detour - Learning React
date: "2019-07-20T23:46:37.121Z"
description: Working on mini React projects to deepen my understanding
---

### Contextual Learning

I am an advocate for contextual learning: trying to tackle a problem first and then learning the material required to solve it. 

This is the approach that I intended to use when working on Guildd, the first Open Source project I was contributing to. However, it was becoming apparent that the gaps in my knowledge for the tech stack were a blocker to my ability to contribute in a meaningful way. In particular, I was struggling to implement React features. Though I had built a project using React before, I had barely scratched the surface of the main concepts, let alone understand the context in which the advanced concepts could be used. 

To gain a better understanding of what *could* be done using the React library, it seemed pertinent to take a React course. By doing this, I hoped to gain a high level understanding of all the features available with React and in what context one might be favourable over the other. 

Keeping sight of the end goal - contributing to Guildd - I decided to timebox my learning of React to a weekend. 

### React Course

#### What is React

React is a JavaScript library, meaning that it runs in the browser (rather than on a server), meaning that it loads instantly.

React components make it easier to work in teams and makes maintenance of code more manageable.

Most web pages are made up of building blocks that look similar to one another. By building these with React components, you don’t have to repeat your code as you would have to do when writing in vanilla JS.

React is the logic behind each of the components. 

ReactDOM renders the components.

Babel (a preprocessor which is responsible for parsing the JSX) is used so that we can write JS in the way that we want and then ship our code to the browser in a way that is usable.

React is about focussing on what you can see and on the logic, rather than the how in between.

#### Why React

React allows you to focus on the business logic rather than on stopping the page from exploding.

React is also maintained by a huge community and has a large ecosystem. This means that there will normally be a solution to the problems that we are trying to solve.

#### Props and State

Pass properties of state down to chilren. 

Update state immutably.

#### How to use React

Use npm (or yarn) as dependency management tool. 

Use Bundler (in this instance Webpack) to bundle all of our files together.

Use Compiler (Babel) that translates modern JS features into workarounds that also work on older browsers. Babel can be hooked into the Webpack configuration so that it is part of the bundler process.

Development server so that we, as a developer, can see what we’re building.

#### Stateful and Stateless

Stateless vs stateful / presentational vs container component

Stateful:
- when a component is managing state
- historically meant a class based component
- since React 16.8, hooks (which are functional based components) can ‘use state’, therefore manage their own state

Stateless:
- a.k.a. presentational or ‘dumb’ components
- historically have always been functional components (because prior to react 16.8 these components could not manage state)
-  you want to have many presentational components (or as few container components as possible) that do not manage state. 
- Why? By splitting the stateful and dumb components, you make the app manageable. You have a nice workflow: you know where your state changes and the other presentation components are only there to render user interfaces. The dumb components only define on external inputs, props, making them highly predictable and therefore making the app easier to maintain.

#### Component Lifecycle

- only available in class based (there is an equivalent in functional components)
- to fetch data from the web
- do some clean up before a component is removed from the DOM

#### When to optimize

It might seem logical to add `React.memo()` or `shouldComponentUpdate` to all components:
* every functional component could be wrapped with React.memo().
* every class based component could implement shouldComponentUpdate.

Is this sensible?
Not always. Somme components will nearly always update when their parent updates. In such cases, adding `React.memo()` or `shouldComponentUpdate` slows down the app because of the additional code that is now being executed.

Evaluation:
Is this component related to a parent component that could change but does not effect the current component in any way? Then a check will be useful. 

