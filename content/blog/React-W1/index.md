---
title: Advanced React 
date: "2019-09-02T23:46:37.121Z"
description: React Hooks
---

Having built a [sample project](https://github.com/MaxRobertsDear/Buger-Builder-React) using the containers / presentational components structure, I was curious about whether it might be easier to follow the flow of data (and whether the components managing state might be easier to test) using hooks instead of class-based components. 

So, I set out to completely re-structure my project by replacing the class based components with hooks. To approach this task with a bit more confidence, I built a mini side project to practice using hooks and understand the context in which they may be helpful. 

Below are my notes on each of the hook methods:

### useState()

* takes an initial state
* useState() returns an array containing two elements
* the first element is the current state
* the second element is a function that can be used to manipulate the state

Using array destructuring, an example may look like this:
``` bash
const [todoName, setTodoName] = useState('')
const [todoList, setTodoList] = useState([])
```

In the first instance, todoName is the current state of a list item and setTodoName is a function that can manipulate that state. 

The todoList is an array (which can be used to store a list of todoNames with `setTodoList(todoList.concat(todoName))` which can be manipulated with the setTodoList function.