# Class 06

_Reading_

[How to use Random Module](https://www.pythonforbeginners.com/random/how-to-use-the-random-module-in-python)

[What is Risk Analysis](https://www.edureka.co/blog/risk-analysis-in-software-testing/)

[Test Coverage](https://martinfowler.com/bliki/TestCoverage.html)

_Videos_

[Big O Notation](https://www.youtube.com/watch?v=v4cd1O4zkGw)

_Bookmark and Review_

[Python Random](https://docs.python.org/3/library/random.html)

Further Reading

[What is Dependency Injection](https://www.freecodecamp.org/news/a-quick-intro-to-dependency-injection-what-it-is-and-when-to-use-it-7578c84fa88f/)

_How can the random module be utilized in Python to generate random numbers or make selections from a list, and what are some common functions available within the module?_

It can be utilized to make shuffled word passwords, do a random operation for a game program, create reandom strings, and shuffle container objects like lists. 

- The randint() Function - generate a random integer in a given range. Takes 2 numbers as input, start & end of that range. If start is bigger than stop in the range, you get a ValueError.
- The random() Function - generate random number between 0 & 1, which returns a floating point number. If you want a larger number, you can multiply it by a larger value or negative numbers for a negative number. 
- The choice() Function - used to select a random element from a list, set, tuple, etc. Takes the collection object as an input. Empty list creates an IndexError. 
- The choices() Function - select 2 or more elements randomly with replacement from a list. Takes the list as its first input, an the values to be selected as the input for its parameter `k`. Returns a list of selected values from the input container object. i.e. `color= random.choices(colors, k=3)`, where `colors` is the container & 3 is the number of random choices in the output you wanted. `k=0` returns an empty list. You can also give `k` a bigger number than the amount in the list, it will just keep generating random choices from what the list is. If you select multiple elements from an empty list, you will get an IndexError. 
- The shuffle() Function - takes a list as an input. Returns the elements shuffled in place. 
- The randrange() Function - input is start, stop, and step. It returns a randomly selected element from the `range(start, stop, step)`

```
  import random
number=random.randrange(0,100,20)
print("The random number is:",number)
Output:
The random number is: 20
```

_In the context of software development, what is risk analysis, and what are the key steps involved in conducting a risk analysis for a software project?_

It is the process of identifying the risks in what you just built and prioritizing them to test. 

List of possible risks you could encounter while building software to assess at the beginning of a project:

- Use of new hardware
- Use of new technology
- Use of new automation tool
- The sequence of code
- Availability of test resources for the application

Here is a direct quote from what risks I can't avoid & what I can do about it, since I don't have the capacity to summarize this more:
"
Risks:
1. The time that you allocated for testing
2. A defect leakage due to the complexity or size of the application
3. Urgency from the clients to deliver the project
4. Incomplete requirements
What can be done:
1. Conduct Risk Assessment review meeting
2. Use maximum resources to work on high-risk areas
3. Create a Risk Assessment database for future use
4. Identify and notice the risk magnitude indicators: high, medium, low."

Types of risk:
1. business business business, numbers (outside of your project, maybe from customer or company)
2. testing risks of the software you're working with
3. premature release risk associated with releasing untested or unfinished software
4. general software risks

Risk analysis: 
1. Searching the risk
2. Analyzing the impact of each individual risk
3. Measures for the risk identified

_What is test coverage and why is it an important (or potentially misleading) metric in software testing?_

It is a good way to find untested parts of your code. 

Quote for good testing from author:
"You rarely get bugs that escape into production, and
You are rarely hesitant to change some code for fear it will cause production bugs."

_What is Big O notation, and how is it used to describe the performance of an algorithm? Give an example of an everyday task (not software related) that demonstrates O(n) time complexity._

How  time scales with respect to some input variables. 
1. If you have different steps of your steps, add up those steps of your algorithm
2. Drop constants
3. If you have different inputs, you will use different variables for them
4. Drop non-dominate terms 

0(1) - doesn't take longer for the size of the data 
0(n) - scales linearly with the amount of data 


_Dependency Injection Notes_
+ a technique where one object or static method supplies the dependencies of another object
+ a dependency is an object that can be used, like a service
+ "transferring the task of creating an object to someone else & using the dependency created by that object is a dependency injection
+ dependencies can be injected at runtime rather than at compile time
+ a class should depend on abstraction of responsibility and not on creating the objects that fulfill that responsibility  -- dependency injection provides the class with the required objects 

Direct quote summary:

- constructor injection: the dependencies are provided through a class constructor.
- setter injection: the client exposes a setter method that the injector uses to inject the dependency.
- interface injection: the dependency provides an injector method that will inject the dependency into any client passed to it. Clients must implement an interface that exposes a setter method that accepts the dependency.

So now its the dependency injection’s responsibility to:

- Create the objects
- Know which classes require those objects
- And provide them all those objects

Libraries and Frameworks that implement DI
- Spring (Java)
- Google Guice (Java)
- Dagger (Java and Android)
- Castle Windsor (.NET)
- Unity(.NET)
