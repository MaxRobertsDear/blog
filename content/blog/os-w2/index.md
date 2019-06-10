---
title: TDD - Chicago vs London Style
date: "2019-04-21T23:46:37.121Z"
description: Investigating the difference between unit and feature testing
---


In Test-Drive Development(TDD), software developers write tests for units of code before writing the implementation code:  

Step 1 - write an expectation within the testing suite. 
   
Step 2 - run the test and watch it fail.  
  
Step 3 - write just enough implementation code to make the test pass, using the error message from the failed test as a guide.  
  
Step 4 - run the test again. If it fails, the implementation code needs updating. If it passes, time to move on to writing the next expectation in the testing suite and build out the programme.  
  

The above cycle is referred to as [Red, Green, Refactor](https://medium.com/r/?url=https%3A%2F%2Fblog.cleancoder.com%2Funcle-bob%2F2014%2F12%2F17%2FTheCyclesOfTDD.html): write a failing test (red); write just enough functional code to pass the test (green); refactor. 
  
*This changes design from a process of invention, where the
developer thinks hard about what a unit of code should do and
then implements it, to a process of discovery, where the developer
adds small increments of functionality and then extracts structure
from the working code.*


Advantages of TTD include:
  
* simpler code, by encouraging programmers to write the bare minimum to fulfil the acceptance criteria.
* breaking problems down into smaller, more approachable challenges.
* fewer bugs - although the capital investment of time associated with writing tests is high with TDD, it will likely significantly reduce the amount of time spent fixing bugs further down the line.
* safer refactoring, by virtue of having tests to warn you if you accidentally change the behaviour of the implementation code. 

### Object-Orientated Programming
*An Object-Orientated Programme (OOP) is  organised around data (or objects) rather than functions and logic. OOP's are made up of a web of objects that interact with each other.* 
  
Further benefits of OOP :

* Encapsulation - enforced by a defined boundary or class. The state of each object is privately held within these. Other objects do not have the ability to make changes to this class, however, they are able call a list of public functions or methods. Hiding data in this way ensures greater programme security by avoiding minimising data corruption. It also makes it easy to modify software by changing how objects are composed together into an application. 
* Abstraction - only code that is relevant to the object calling for information is shown. All other implementation code remains hidden, thus making it easier for developers to modify the programme.
* Inheritance - any subclass can inherit the definitions of one or more general classes. There is an inherent validity to this process: anything that works for the general class will also work for the subclass, thereby reducing development time.
* Polymorphism - different meaning or usage can be assigned to an object depending on the context, which is determined by the programme. This mitigates the need for duplicating code.

### Integration and Unit Tests
Two ways to write your tests are integration testing (or feature testing) and unit testing. Integration tests (otherwise referred to as the Chicago style tests) reveal whether a feature is working by invoking one or more software methods or features. Unit tests (a.k.a. London style tests) test a single method in isolation by assuming that the rest of the software/dependencies work as expected. This is achieved by mocking the behaviour of the dependencies. 
  
For example, if writing a test for an 'Order' class of a takeaway (below syntax is written in RSpec) which depends on objects encapsulated within a separate 'Menu' class:
  
```
# London Style
describe Order do
  let(:menu) { double :menu, price: '£1.00', contains?: true }
  subject(:order) { described_class.new(menu) }

  it 'order total to be sum of items added' do
    order.add('Pizza')
    order.add('Pizza')
    expect(order.total).to eq '£2.00'
  end
end
```
```
# Chicago Style --> arguably an 'integration' or 'feature' test
describe Order do
  subject(:order) { described_class.new(Menu.new) } # note real Menu class

  it 'order total to be sum of items added' do
    order.add('Pizza')
    order.add('Pizza')
    expect(order.total).to eq '£2.00'
  end
end
```

### Instance Doubles
Why a hybrid between the London and Chicago approach might be worth while:
  
* London style focuses on testing the behaviours of a class in isolation
* Chicago style ensures that the implementation code does what it's meant to
  
A hybrid between the two may be advantageous: develop the programme using isolated unit testing and follow it up by turning doubles into instance doubles to ensure that there isn't any functional code missing.