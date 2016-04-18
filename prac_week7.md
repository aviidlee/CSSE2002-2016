# Things you should learn
- How to write a recursive method

# Questions to ask yourself when writing recursive methods
- What is your base case? The trivial easy case you can solve?
- How can you state your problems in terms of subproblems? 
- Does your recursive method always bottom out to your base case?

# Further help on recursive methods:
- The key is to break the problem into smaller subproblems; does the
   problem require you to perform some action over and over again? 
   Look up ``Divide and conquer''
   
- Remember that your method must have a **base case**; otherwise it will
   recurse forever and never return! The base case is the smallest, trivial case.
   For instance, if you were trying to find the minimum element in a list of 
   integers, the base case would be if the list just contains one integer (then you
   just return that integer, there is no problem to solve). 

- Remember that your problem must **get smaller** at each recursive call 
   (otherwise it will not get to the base case, and you will loop forever); 
   e.g., if you are dealing with lists, then each recursive call should be on 
   a smaller list. 
   
- If you are stuck, do it with pencil and paper first. If someone gave you a 
   word and asked you whether or not it was a palindrome, how would you figure out
   the answer? If you had to teach a toad how to reverse a string, what would you 
   tell it? 
   
# Java tips:
- None of these methods require you to keep a reference to instance variables, so 
   you can make them static. 
    
# 19.5
- If you just put ``public void reverse(List<E> list)'' then the compiler will be annoyed
   because it will think that `E' is a concrete type (like String, HashSet etc), but of course
   you mean a **type parameter** not a type. To fix this, you need to put
   public <E> void reverse(List<E> list). 

- **WARNING**: subList returns a *view* not a new list that is a sublist of the original. 

# Exercise 2 
- Note that while `HashSet<Set<Integer>>` is considered a subtype of `Set<Set<Integer>>`, `HashSet<HashSet<Integer>>` is not.
  This will be covered later in the course, but if you are curious, you can read the documentation [here](https://docs.oracle.com/javase/tutorial/java/generics/inheritance.html).
