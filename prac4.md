# Hints and Tips for Assignment 1

## Invariants 
- Recall the definition of invariants and what they are for.
- Look at the constructor of the class; does it specify anything about valid states of the class?
- If the class is mutable, in what way is an instance allowed to change? 

## Hashcodes 
- See lecture slides for requirements. Remember that two objects which are equal must have equal hashcodes.
- For Location: the only tricky part is dealing with two locations which are equal but have different offsets.
Is there some way that you can standardise the way the offsets are measured? 

