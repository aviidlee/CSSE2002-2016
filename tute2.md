# Things you should learn
- Understand scope and aliases 
- Understand the difference between declaring and instantiating
- Translate real world objects into specifications and code

## Scope and aliases 
- Remember from last week: difference between primitive and reference types
- Question 1

## Declaration and instantiation 
- Consider the following lines of code:

        int x;
        int[] array;
    
  What is the value of x and of array? 
- Do Question 2
- How do you fix the code so that you no longer get the Exception? 

## Translating real world to abstract code
- Ask yourself: 
    - what are the important properties/states? -> instance variables and queries
    - what can you do to the object/what can the object do? -> methods that change instance variables
- Try Question 1.3

## Implementation Invariants 
- What are they for? 
- How do we maintain them? 

         /* What is wrong with this code? */
         class Wizard {
           public int health;
           
           public void fireSpell() {
             // stuff
           }
         }
         
         /* what about this code? How should we change it? */
         class Troll {
           private ArrayList<Weapon> weapons;
           private int health;
           private int defence;
           
           public ArrayList<Weapon> getWeapons() {
             return weapons;
           }
         }
         
          /* what about this code? How should we change it? */
         class Warrior {
           private ArrayList<Weapon> weapons;
           
           public void setWeapons(ArrayList<Weapon> weapons) {
             this.weapons = weapons;
           }
         }
