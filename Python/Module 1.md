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
