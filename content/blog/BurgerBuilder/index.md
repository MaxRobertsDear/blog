---
title: React App - Side Project
date: "2019-08-04T23:48:37.121Z"
description: A deep dive into the code I've written for a side project that I have been working on
---


https://www.youtube.com/watch?v=2lsXtHzSUOM&feature=youtu.be

Here's a video that I have recorded, diving into the code for a side project that I have been working on. 

#### Video Contents
- project overview (what does it do)
- lifecycle hooks (and the order in which they execute)
- deep-dive into two components 
<Burger /> - using .map().reduce() to dynamically render data
<BuildControls /> - using local state to pass down event handlers
(I might suggest viewing this at 2x normal speed)

#### Technologies/patterns used (and reasons why)
- axios for HTTP request (I use the interceptors methods for error handling)
- class-based components for managing state (as opposed to using hooks)
- module.css (for scoped css classes)
- containers / presentational component project set-up (easy project navigation of the flow of state)
- local state for passing down eventHandlers (wanted to practice using straight up react before using third party libraries such as Redux)

#### Next Step
Next, I aim to update my class-based components to leverage React Hooks. Depending on who you're working with, future projects that I will be working on may either use class-based components for managing state or React Hooks. As such, I want to know how to use both.