# Things you should learn 
- Partial and total correctness: proof 
- Loop invariants: why and how to come up with them 

# Partial and total correctness
- Definitions 

	## Question 1
	a.
	b.
	c.

# Loop invariants 
- Some statement which is true before you enter the loop (base case)
  and after every iteration of the loop
  	- Usually stated in terms of the i-th iteration of the loop
  	  E.g., after the i-th iteration, j > i

- Can use to prove that method is correct 
	- Try to choose an invariant which resembles your postcondition;
	  indeed, in many simple cases, upon termination of the loop the 
	  loop invariant will *be* the postcondition

	## Example 

		/**
		 * @require list != null, list.size() > 0
		 * @ensure for all 0 <= j < list.size(), list.get(j) <= \result
		 */
		public static int max(List<Integer> list) {
			int max = list.get(0);

			for(int i = 1; i < list.size(); i++) {
				max = Math.max(list.get(i), max);
			}

			return max;
		}

	
	## Question 2
	- Reminder about what partition does 
	- To come up with loop invariant, have a look at postcondition 

	# Question 3
	



		
