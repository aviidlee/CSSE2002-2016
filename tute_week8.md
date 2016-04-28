# Assignmet 2 Hints 
- A quick primer on file parsing and exception handling 
- Understanding difficult specs: the Allocator class.

## Getting started
- Do the IO stuff first 
- Always read the documentation of the classes you use very carefully!

  ### TrackReader 
  - Read the examples of correctly-formatted and incorrectly-formatted files 
  - You might want to try writing it without the error checks first, and then add the checks later
  - **Note**: the code will expect to find the file under the project directory, rather than inside src.
  
    #### Reading and parsing files 
    - Lots of ways to do it, but will show you a one:
      - Scanner can be defined on a File and on a String (among other things) 
      - Has useful methods: hasNext(), next(), nextInt() etc. 
      - Space-delimited by default, but can change that. 
      - If you are brave, you could also try using regular expressions with methods like findInLine
      
    - E.g., suppose you have a file in which each line has data about a person: 
    
      ```
      Potter 10 Wand
           Gandalf 100 Staff        
      Voldemort      30 Wand
      ```
      For demo, use `String wizardData = "Potter 10 Wand\n   Gandalf 100 Staff   \nVoldemort      30 Wand"`
      You want to read the file and make a `Wizard` object from each line. For now, just print stuff.
      Then you have to read each line, and have to do some processing for each line.
      
      ```java
      Scanner scanner = new Scanner(new File("wizardsData.txt"));
      while(scanner.hasNextLine()) {
        String line = scanner.nextLine();
        Scanner lineScanner = new Scanner(line);
        String name = lineScanner.next();
        int level = lineScanner.nextInt();
        String weapon = lineScanner.next();
        System.out.println(String.format("Wizard called %s is at level %d and wields %s", name, level, weapon));
      }
      ```
      Notice how it automatically stripped the extra whitespace for us.
      
    #### Exception handling 
    Basic structure: 
    ```java
    try {
      awesome code
    } catch(IOException e) {
      handle exception here 
    } catch(SomeOtherException e) {
      handle the other exception
    } 
    ```
    - Unhandled Exceptions propagate up the chain of callers 
    - Remember you can next try-catch blocks if you need to 
    - Don't manually check for exceptions that an existing class can check for you.
    
      E.g., suppose that from the above wizard-parsing code, we want to make actual Wizards. 
      To make a valid Wizard, the Wizard must have a String name, an integer level < 1000, and a valid Weapon,
      as defined by the constructor of Weapon. So Weapon constructor throws its own exceptions if you give it bad inputs,
      maybe like a nonsensical weapon such as toilet paper. The Wizard constructor also throws exceptions, for example
      if you give the Wizard a non-magical weapon. 
      
      ```java 
      class Wizard {
        public Wizard(String name, int level, Weapon weapon) throws BadWeaponException {
         ...
        }
        ...
      }
      
      class Weapon { 
        public Weapon(String name) throws BadWeaponException {
        ...
        }
      }
      ```
      
      But, say that your file-parsing method is only allowed to throw BadWizardFileExceptions.
      Then you could do stuff like: 
      
      ```java 
      try {
        // weaponString, name and level were read from a file
        Weapon weapon = new Weapon(weaponString);
        Wizard wizard = new Wizard(name, level, weapon);
      } catch(BadWeaponException e) {
        throw new BadWizardFileException(e.getMessage());
      }
      ```
      Here, we didn't do any checking ourselves, because everything that could go wrong here is checked 
      by the constructors of the Weapon and Wizard classes. 
      
  ### The Allocator class
  - Read the specs VERY VERY carefully, and draw diagrams.
  - Ask yourself what the simplest possible cases are.
  - Read through the test cases. Draw yourself a picture of the track.
