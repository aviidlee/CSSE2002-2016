# CSSE2002 Week 12 Tute 

## What you should learn
- Difference between overloading and overriding
- How to figure out which method is called when using overriden/overloaded methods
- Learn how to apply the substitution principle

## Cheatsheet (from lecture notes)
### Overloading and overriding
- Overloaded - declared type 
- Overriden - actual type 

- Procedure:
	```java
	Animal animal = new Dog();
	animal.makeNoise(Situation s);
	```
	- Choose a method based on declared type Animal; a makeNoise(Situtation s)
	  in Animal or in the closest superclass. 
	- If the method is overriden in Dog, choose this method. Otherwise stick
	  with original choice.

- Designing for extension 
	- Use protected methods to access private instance variables 
	- Constructor must not invoke overridable method
	- Document use of overridableb method

### Wildcards
- `Stuff<Dog>` is NOT a subtype of `Stuff<Animal>`
- But `Stuff<Dog>` is ok to use in place of `Stuff<?>`

## Q1
- Keep track of program state 
- Procedure:
	```java
	Animal animal = new Dog();
	animal.makeNoise(Situation s);
	```
	- Choose a method based on declared type Animal; a makeNoise(Situtation s)
	  in Animal or in the closest superclass. 
	- If the method is overriden in Dog, choose this method. Otherwise stick
	  with original choice.

## Q2
- Substitution principle: objects of type T can be replaced by object of subtype S.
  This means that subtype's *overriden* method satisfies the supertype's specs;
  so for the subtype, the precondition must be at least as weak, and the postcondition
  at least as strong.

## Q11.5
- What is an abstract class? 

- A non-instatiable class intended for subclassing, may or may not have abstract methods.
	- for sharing code among related classed
	- abstract method is a method without implementation. 
	- unlike in interfaces, can have non-public non-static instance variables.
	- can implement an interface

```java
public abstract class Animal {
	public abstract void makeNoise();
}
```
- What functionality is common among all pieces?

## Q20.5 & Q20.6
Syntax:
```java
public static <T> List<T> remove(int n, List<T> list) {
	...
}
```
