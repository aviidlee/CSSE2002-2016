# Week 9 Tutorial 
## Things you should learn
- Practise object-oriented design 
- Throwing and catching exceptions 

## Q15.1
- The enrol method is not great because exception is being used handle a normal
  case and not an error case; bad communication

- We could instead do the following:
	- Changing enrol: 
        - Don't use indexOf. Instead you could do 'contains' to check that if the list 
          contains the student. This would increase runtime though. 
        
        - Instead of using a List, use a Set. If the interface insists on a List, you 
          can always add the items in the Set to a List. 
       
    - Changing indexOf:
		- Change spec so that it returns -1 or some other recognisably special, non-index
		  value if it cannot find the item. 

		- Require that the item is on the list, but this is silly because to determine
		  whether or not an item is in the list would take just as much work as finding the index

## Q15.2

## Q15.3

## Q1
