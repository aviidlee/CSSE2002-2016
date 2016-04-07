# Hashcodes 
- Basic ideas is taking an object and assigning it its address. 
- Two methods which are equal must have equal hashcodes. 
- Two objects which are not equal should *ideally* have different hashcodes. 

# The equals method vs. == 
- Only use == if you are comparing primitive types, or want to know if two objects 
  are literally the same things in memory. 
  
# Basic string manipulation (for toString)
- For really simple things, using + is fine, but for more arduous manipulations: 

  ## String.format 
      String string = String.format("I have %d cakes and %d cookies, baked for my friend %s", 2, 3, "John");
  
  `%d` for integers, `%s` for Strings. 
  
  ## StringBuilder - good if you need to join a lot of strings together
      StringBuilder sb = new StringBuilder(); 
      // You could stick the append in a for loop or something
      sb.append("My name is ");
      sb.append("not Mary.");
      sb.append(56);
      String sentence = sb.toString();
    
# Coming up with invariants 
- These are NOT necessarily complex or numerous! 
- Look at the constructor of the class; does it specify anything about valid states of the class?

## Some notes 
- Your invariants will depend on your implementation, because they say things about the 
  state of and the relationship between your instance variables. 
- You do NOT need to state invariants which are properties of your instance variables;
  e.g., in the Location class, don't state invariants of Section. 
  
# Protecting invariants 
- No public instance variables 
- Don't set a mutable instance variable to something passed into the class
- Don't return a mutable instance variable (copy it first) 

# Testing 
- Remember, edge cases and boundary cases 
- Start with blackbox test cases, then if you have time, try to do some whitebox ones as well. 

# Commenting 
- You do NOT need to comment every line! Comment guidelines are in the assignment sheet. 
