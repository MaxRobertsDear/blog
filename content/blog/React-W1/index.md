---
title: Advanced React 
date: "2019-09-02T23:46:37.121Z"
description: React Hooks
---

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