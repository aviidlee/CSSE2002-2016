# Hashcodes 
- Basic ideas is taking an object and assigning it an address. 
- Two methods which are equal must have equal hashcodes. 
- Two objects which are not equal should *ideally* have different hashcodes. 

# The equals method vs. == 
- Only use == if you are comparing primitive types, or want to know if two objects 
  are literally the same things in memory. 
  
# Basic string manipulation (for toString)
- For really simple things, using + is fine, but for more arduous manipulations: 

  ## String.format 
      String string = String.format("I have %d cakes and %d cookies, baked for my friend %s", 2, 3, "John");
      // string is now "I have 2 cakes and 3 cookies, baked for my friend John"
      
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
- If the class is mutable, look at what types of changes to its state are allowed. 

  ## Some notes on invariants 
  - Your invariants will depend on your implementation, because they say things about the 
    state of and the relationship between your instance variables. 
  - You do NOT need to state invariants which are properties of your instance variables;
    e.g., in the Location class, don't state invariants of Section.

  ## Example for an immutable class
      class Fight {
      	private Fighter fighter1;
      	private Fighter fighter2;
      	private Fighter winner;
      	
      	/**
      	 * Invariants:
      	 * - winner != null 
      	 * - f1 != null && f2 != null
      	 * - !f1.equals(f2)
      	 * - f1.equals(winner) || f2.equals(winner)
      	 */
      	 
      	/**
      	 * Create a new fight with the given fighters and winner
      	 * 
      	 * @throws NullPointerException if f1, f2 or winner is null
      	 * @throw InvalidFightException if f1.equals(f2)
      	 * @throw InvalidFightException if winner is not equal to one
      	 * of f1 or f2.
      	 */ 
  	      public Fight(Fighter f1, Fighter f2, Fighter winner) {
  	          // Stuff
  	      }
  	   }
  	   
  ## Example for a mutable class
      class Tavern {
        // This is like a Python dictionary - keys are Strings, values are integers.
      	private HashMap<String, Integer> inventory;
      	
      	/**
      	 * Invariants: 
      	 * - inventory != null 
      	 * - none of the elements of inventory are null
      	 * - for any drink in inventory, there are 0 or more barrels of that drink.
      	 */ 
      	 
      	/**
      	 * Create a tavern with an empty inventory 
      	 */
      	public Tavern() {
      		inventory = new HashMap<....>();
      	}
      	
      	/**
      	 * Add the given number of barrels of the specified drink to
      	 * the inventory. 
      	 * @require drink != null, barrels >= 0
      	 *
      	 * @param drink the drink for which we are adding stock 
      	 * @param barrel the number of barrels of the drink to add to stock
      	public void addStock(String drink, int barrels) {
      		
      	}
      
      	/**
      	 * If requested barrels of specified drink available, 
      	 * serve it by subtracting barrels from the stock for that drink, 
      	 * else throw YouDrinkTooMuchException.
      	 * 
      	 * @require drink != null, barrels >= 0
      	 * @param drink the drink which we are serving 
      	 * @param barrels the number of barrels of the drink to serve
      	 */
      	public void serveDrink(String drink, int barrels) throws YouDrinkTooMuchException {
      		
      	}
      }
  
# Protecting invariants 
- No public instance variables 
- Don't set a mutable instance variable to something passed into the class
- Don't return a mutable instance variable (copy it first) 

# Testing 
- Remember, edge cases and boundary cases 
- Start with blackbox test cases, then if you have time, try to do some whitebox ones as well. 
    
    ## Example: sorting method 
        /**
         * Sort array into non-decreasing order
         */ 
        public void sort(int[] array) {
        	....
        }
        
        Test cases: 
        Input 			Output 			    Notes 
        [] 				    []            Test emtpy array
        [1]				    [1]           Test array with just one element
        [3, 1, 2]		  [1, 2, 3]     Typical case 
        [-3, -2, -1]	[-3, -2, -1]  Case with negative numbres 
        [3, 2, 1]		  [1, 2, 3]     Descending list 
        [2, 1, 1]		  [1, 1, 2]     Repeated elements 
        [-3, 1, -2]		[-3, -2, 1]   Mixed positive and negative numbers 


# Commenting 
- You do NOT need to comment every line! Comment guidelines are in the assignment sheet. 
- Make sure to comment your instance variables and local variables that are not for loop variables. 
- Make the comment *helpful*; don't just repeat the code! 
    ## Example from the Tavern class
    ### A BAD comment
        // A HashMap representing the inventory of this tavern
        private HashMap<String, Integer> inventory;

    ### Better comment 
        /* An inventory of the tavern storing the number of barrels 
      	 * of a given drink that is in stock
      	 */
      	private HashMap<String, Integer> inventory;
    
