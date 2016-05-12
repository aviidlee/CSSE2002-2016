# Week 10 Tutorial

## What you should learn
- What Java Interfaces are and why we use them
- How to write and implement interfaces

## Interfaces
- A specification saying what a class does
- At a code level, a bunch of methods with empty bodies that are related in some way
- Allows flexibility; allows your code to be used with a variety of different classes
	- E.g. your code works for any class that implements List, as opposed to
	  working just for ArrayList and its subclasses
	- You can use the library sort method for a custom container class you 
	  write, as long as you implement List

### In comparison with inheritance
- A class can implement multiple interfaces but can only inherit from
  one class
- Cannot instantiate an interface, and an interface contains no implementation
  except for default methods

### Some advanced questions
- What happens if you need to change an interface? 
- What happens if you implement two interfaces that have methods with identical 
  signatures?
  
## Q 9.4
## Q 9.7
