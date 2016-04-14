# Things you should learn/do
- How to write pre and postconditions 
- Understand why we write pre and postconditions 
- Write blackbox tests
- Write whitebox tests

# Pre and postconditions

  ## Motivation
  - Makes expectations super clear
  - We can actually prove that a method is correct
  - Makes code simpler to write because we're not trying to deal with every possible input
  
  ## Tute 4 Ex 5.7
  - Consider lower and upperbounds for parameters 
  - Postconditions are usually written in terms of the original values of the parameters
  
  ## Tute 4 Ex 5.11
  
# Black-box tests for partition
- Boundary cases and typical cases 

# White-box tests for partition 
- Want 0, 1, and 2 times through the for loop.
    - Why? 0 and 1 are kind of edge cases, 2 is kind of like the normal case; just seems
      to work; have run into cases where code worked for 1 iteration of loop but not 2. 
- Different levels of coverage

          public void example(int x, int y) {
            int i, j;
            if(x > 0) {
              i = x*x;
            } 
            if(y > 0) {
              j = y - 1;
            }
            return i + j;
          }
      
    - statement: execute every statement (so, think of as every line gets run)
        - E.g., cover just TT 
    - branch coverage: every branch (paths taken by the code decomposes the tree)
        - E.g., covering TT and FF
    - path coverage: every path through the conditional tree
        - E.g., covering TT, TF, FT, FF
