# CSSE2002 Prac 1

## Things you should learn from this prac
- Import and run code in Eclipse
- Use and modify code without fully understanding how it works (abstraction)

## Helpful tips
### Using Eclipse 
- If Eclipse doesn't launch on the lab machines, try running it as administrator.
- There is a *Getting started with Eclipse* guide on the course materials page. 
- The root directory is the project directory. Suppose you have a project structure like this:
  <pre><code>
  PracProjectFolder
    |_ src
    |   |_mypackage
    |        |_ MyClass.java
    |_ someFile.txt`
  </code></pre>
Then to tell Eclipse where to find `MyClass.java`, you need to say `src/mypackage/MyClass.java`,
and to tell it where to find `someFile.txt`, you need to say `someFile.txt`.  

### ShapeViewer.java
- This program requires a *commandline argument*; the user needs to give it
  some information about what to do, namely the number of vertices the shape
  should have. 
    - The program's `main` function deals with commandline arguments.

- To give the program commandline arguments, go to 
  `Run > Run Configurations > Java Application > ShapeViewer > Arguments`
  and then type in the argument into `Program arguments`.

### Neko 
#### Troubleshooting questions 
- Where does the program expect to find the images? In the `src` folder?
  In a package? Or somewhere else? 

