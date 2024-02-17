# Class 1 - O Notation, Names and Values in Python

## Bookmark [Python 3 Module of the Week](https://pymotw.com/3/index.html), articles on how to use Python.

_In the context of the reading “Pain and Suffering,” describe the main challenges faced by beginners when learning Python and suggest at least two strategies for overcoming these obstacles._

It seems like the main challenges are figuring out things for yourself, working outside your comfort zone, and learning to handle the emotional temperature of yourself and others. 

- Research, but with a goal in mind. Looks for similar questions being asked on Stack. Ask the TAs.
- Manage your time with your spirit.
  
- My main challenge is overwhelm with how much I need to learn & the anxiety of inadequacy in general. The way I've coped with this before is just to keep going anyway, even if I think I can't do it.
- I am hoping to stay balanced. Though my heart is not clear, I aim to rise above suffering.

_After reading “Beginners Guide to Big O,” explain the concept of time complexity and space complexity._

The time complexity is how long the program will run in proportion to the data being input. 
The space complexity refers to how much space a program will need to run. 
Both time and space required relate to algorithmic proficiency. 

**Notes for future reference for me:
**
- O(1) describes an algorithm that will always execute in the same time (or space) regardless of the size of the input data set.
- O(N) describes an algorithm whose performance will grow linearly and in direct proportion to the size of the input data set
- O(N²) represents an algorithm whose performance is directly proportional to the square of the size of the input data set (common with nested iterations)
- O(2^N) denotes an algorithm whose growth doubles with each addition to the input data set. Exponential.
-  O(log N). The iterative halving of data sets described in the binary search example produces a growth curve that peaks at the beginning and slowly flattens out as the size of the data sets increase e.g. an input data set containing 10 items takes one second to complete, a data set containing 100 items takes two seconds, and a data set containing 1,000 items will take three seconds. 

_Based on the “Names and Values in Python” reading, explain the difference between mutable and immutable data types in Python._

Mutable values can have multiple aliases, where as immutable values cannot alias. 

**Notes for me: 
**
Assignment never copies data-- changes are visible through all names of the values. 
a mutable aliasing.

<img width="395" alt="Screenshot 2024-01-24 at 10 55 33 AM" src="https://github.com/maddieamie/reading-notes/assets/118625447/1d59a689-9487-4f78-9f28-0e26775d8510">

immutable values can't alias -- ints, floats, strings, tuples. 

<img width="298" alt="Screenshot 2024-01-24 at 10 58 56 AM" src="https://github.com/maddieamie/reading-notes/assets/118625447/407c5038-30b2-4096-b1d9-e7f7d2320bec">

Write values that return new lists instead of mutating to avoid future confusion, as advice from Ned Batchedler. 

# Class 02 

_What are the key principles of Test-Driven Development (TDD) in Python, and how do they contribute to the overall quality of code?_

Think about and write tests first!

AAA: Arrange, Act and Assert.

Arrange: you need to organize the data needed to execute that piece of code (input);
Act: here you will execute the code being tested (exercise the behaviour);
Assert: after executing the code, you will check if the result (output) is the same as you were expecting.

Your code will be more reliable because it will produce expected outcomes with passing tests. If you craft tests to run the outputs that you need, then when they all pass when you're writing your code, you know you're close to done.


_Explain the purpose of the if __name__ == '__main__': statement in Python scripts. What are some use cases for including this conditional in your code?_

It tests to make sure that the main program is being run directly or if it is being imported by another file. You may want to import different files into the main program, or import the current file into another thing. Maybe your main file is a library that you want others to be able to import, but also you want to be able to run it on its own as a demo or as a tutorial. Maybe you want to import your file to run some unit tests but not run the whole thing directly while testing. 

_Describe the concept of recursion in Python._

You are calling the function you just defined inside itself-- directly or indirectly. 

Properties of Recursion:

- Performing the same operations multiple times with different inputs.
- In every step, we try smaller inputs to make the problem smaller.
- Base condition is needed to stop the recursion otherwise infinite loop will occur.

- [Recursion explained visually article](https://www.freecodecamp.org/news/recursion-visually-explained-bec8cca14d9b/)

- Maybe look up the tower of hanoi problem in smaller contexts. 

_What is the difference between Python modules and packages? Explain how to create, import, and use them in your Python programs._

Create modules by creating viable code in a file.py. Import module files into other modules by using the import statement and using dot notation to utilize the methods within the imported module. Otherwise, you can import modules as this : from <module_name> import <name(s)> to use the object names in imported program without referencing the program itself in the current code. You can also import like this: from <module_name> import <name> as <alt_name>[, <name> as <alt_name> …] to reassign the names of those imported methods to the local call stack. Or you could import the entire module and assign it an alternative name: import <module_name> as <alt_name>. 

Extended use cases : [Python Modules and Packages](https://realpython.com/python-modules-packages/)

**Bookmark and Review**

[Google for Education: Python Lists](https://developers.google.com/edu/python/lists)

[Google for Education: Python Strings](https://developers.google.com/edu/python/strings)

[Python Modules and Packages](https://realpython.com/python-modules-packages/)

[Pytest Documentation](https://docs.pytest.org/en/latest/)

[PyTest Tutorial](https://www.guru99.com/pytest-tutorial.html) Up to section Running tests in parallel

## Class 03 

_General Notes_

- it is the python programmer's responsibility to close a file in your program after you open it using open()
- to iterate over the whole file line by line, it is generally quicker and more memory efficient to use this method: ``` >>> with open('dog_breeds.txt', 'r') as reader:
>>>     # Read and print the entire file line by line
>>>     for line in reader:
>>>         print(line, end='')
Pug
Jack Russell Terrier
English Springer Spaniel
German Shepherd
```
- 

_What is the purpose of the ‘with’ statement when opening a file in Python, and how does it help manage resources while reading and writing files?_

```
with open('dog_breeds.txt') as reader:
    # Further file processing goes here
```
The ```with``` statement takes care of closing the file automatically after leaving the with block, even when encountering an error. It helps make sure that dtata is not remaining open and leaking into other environments outside of your code. It reduces unwanted behavior. You can also open with mode to describe the type of thing you are opening and the expected behavior of that file. 

```
with open('dog_breeds.txt', 'r') as reader:
    # Further file processing goes here
```
|Character | 	Meaning |
|----------- | ------------ |
| 'r'	|Open for reading (default)|
|'w'	|Open for writing, truncating (overwriting) the file first|
|'rb' or 'wb'|	Open in binary mode (read/write using byte data)|


_Explain the difference between the ‘read()’ and ‘readline()’ methods for file objects in Python. Provide examples of when to use each method._

Read() runs based on the size of bytes, where as readline() reads the amount of characters in a line. Readline(5) will print 5 characters in a line. .read() without arguments will print the whole file as a single string. .readlines() returns a list of what is in the file, line by line as a new index in the list. 

Description:
 | Method	| What It Does|
 |--- | ---|
|.read(size=-1)|	This reads from the file based on the number of size bytes. If no argument is passed or None or -1 is passed, then the entire file is read.|
|.readline(size=-1)	|This reads at most size number of characters from the line. This continues to the end of the line and then wraps back around. If no argument is passed or None or -1 is passed, then the entire line (or rest of the line) is read.|
|.readlines()|	This reads the remaining lines from the file object and returns them as a list.|

_Briefly describe the concept of exception handling in Python. How can the ‘try’, ‘except’, and ‘finally’ blocks be used to handle exceptions and ensure proper execution of code? Provide a simple example._

