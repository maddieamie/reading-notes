## Module 2: Integrating The Back End

### Class 06

[What Google Learned From Its Quest to Build the Perfect Team](https://www.google.com/amp/mobile.nytimes.com/2016/02/28/magazine/what-google-learned-from-its-quest-to-build-the-perfect-team.amp.html)

**Quotes**
+ Team members may behave in certain ways as individuals — they may chafe against authority or prefer working independently — but when they gather, the group’s norms typically override individual proclivities and encourage deference to the team.
+ Project Aristotle researchers concluded that understanding and influencing group norms were the keys to improving Google’s teams.
+ The right norms, in other words, could raise a group’s collective intelligence, whereas the wrong norms could hobble a team, even if, individually, all the members were exceptionally bright.
+ ‘‘As long as everyone got a chance to talk, the team did well,’’ Woolley said. ‘‘But if only one person or a small group spoke all the time, the collective intelligence declined.’
+ Second, the good teams all had high ‘‘average social sensitivity’’ — a fancy way of saying they were skilled at intuiting how others felt based on their tone of voice, their expressions and other nonverbal cues.
+ an exam known as the Reading the Mind in the Eyes test
+ as psychological safety — a group culture that the Harvard Business School professor Amy Edmondson defines as a ‘‘shared belief held by members of a team that the team is safe for interpersonal risk-taking.’’ Psychological safety is ‘‘a sense of confidence that the team will not embarrass, reject or punish someone for speaking up,’’ Edmondson wrote in a study published in 1999. ‘‘It describes a team climate characterized by interpersonal trust and mutual respect in which people are comfortable being themselves.’’
+ ‘‘Just having data that proves to people that these things are worth paying attention to sometimes is the most important step in getting them to actually pay attention,’’ Rozovsky told me. ‘‘Don’t underestimate the power of giving people a common platform and operating language.’’

**To what extent did psychological safety impact your previous work experience?**

It greatly impacted the needs of the staff and students, and how well colleagues collaborated with on another.

**How does this article inform your approach to working with others moving forward?**

To be honest, this wasn't new information to me. I am still working on how to connect with others best, but I'm not too bad at it.

[How I explained REST to my brother](https://gist.github.com/brookr/5977550)

**Who is Roy Fielding?**

Wrote the first web servers & did research on how the internet works. His protocol: HTTP. APIS: computer communication.

**Why don’t the techniques that we use in this class work well when we need to be able to talk to all of the machines in the world?**

"Because they weren't designed to be used like that. When Fielding and his colleagues started building the web, being able to talk to any machine anywhere in the world was a primary concern. But most of the techniques developers later used to get computers to talk to each other didn't have those requirements. You just needed to talk to a small group of machines."

**What is the HTTP protocol that Fielding and his friends created?**

"The whole world wide web is built on an architectural style called “REST”. REST provides a definition of a “resource”, which is what those things point to."

**What does a GET do?**

 “polymorphism”: objects have different actions applied to them, different verbs but same nouns. " But HTTP is actually a general purpose protocol for applying verbs to nouns."
Each of the systems would retrieve information from each other using a simple HTTP GET. 

**What does a POST do?**

If one system needs to add something to another system, it would use an HTTP verb of POST. 

**What does PUT do?**

Replaces something in another system. 

**What does PATCH do?**

Does a partial update of a system, similar to PUT.

### Class 07

[An Introduction to Node.js on sitepoint.com](https://www.sitepoint.com/an-introduction-to-node-js)

**What is node.js?**

"Node.js is an event-based, non-blocking, asynchronous I/O runtime that uses Google’s V8 JavaScript engine and libuv library." Event driven--everything happens in relation to an event that occurs. It's capable of handling a lot at once.

**In your own words, what is Chrome’s V8 JavaScript Engine?**

It is an open-source program that allows browers to run on Javascript and to execute Javascript on our own computers.

**What does it mean that node is a JavaScript runtime?**

JS runtime provides features/APIs to build Javascript based software, and adds additional APIs and functionality.

**What is npm?**

NPM is primarily used for managing and distributing open-source JavaScript libraries and packages, making it easier for developers to share and reuse code in their projects.

**What version of node are you running on your machine?**

~ node -v
v20.8.0

**What version of npm are you running on your machine?**

~ npm -v
6.13.4

**What command would you type to install a library/package called ‘jshint’?**

npm install -g jshint

**What is node used for?**

Node lets Javascript run on the server. Real time applications like chat sites, live document edits, or apps that require collaboration. "It’s also a good fit for building APIs where you’re handling lots of requests that are I/O driven (such as those needing to perform operations on a database), or for sites involving data streaming, as Node makes it possible to process files while they’re still being uploaded." It works well with JSON, which is ubiquitous. 

"For example it can be used as a scripting language to automate repetitive or error prone tasks on your PC. It can also be used to write your own command line tool, such as this Yeoman-Style generator to scaffold out new projects.

Node.js can also can be used to build cross-platform desktop apps and even to create your own robots."

![Source: Introduction To Node.js by Prof. Christian Maderazo, James Santo](https://uploads.sitepoint.com/wp-content/uploads/2012/10/1516152673node_event_loop.png)

[6 Reasons for Pair Programming](https://www.codefellows.org/blog/6-reasons-for-pair-programming/)

**What are the 6 reasons for pair programming?**
1. Greater efficiency
2. Engaged collaboration
3. Learning from fellow students
4. Social skills
5. Job interview readiness
6. Work environment readiness

**In your experience, which of these reasons have you found most beneficial?**

I haven't been able to sync up with others for work times in this self-paced, but the chatting about the curriculum has been helpful. I'd like to practice this sometime, maybe I can with some friends I make in the future.

**How does pair programming work?**

Driver creates code and is responsible for doing the physical coding, while the Navigator provides feedback, looks at the big picture, and looks up resources.

**Bookmark and Review**
[Geocoding API Docs](https://locationiq.com/)

[Axios docs](https://www.npmjs.com/package/axios)


**Async Programming Notes**
[MDN Intro to Async](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Asynchronous/Introducing)
[MDN async and await](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Asynchronous/Async_await)

_the problem with synchronous programming_

+ "At each point, the browser waits for the line to finish its work before going on to the next line. It has to do this because each line depends on the work done in the preceding lines." This is synchronous programming.
+ What if the synchronous function takes a long time to run?
+ Async functions: Start a long-running operation by calling a function.
Have that function start the operation and return immediately, so that our program can still be responsive to other events.
Notify us with the result of the operation when it eventually completes.
  


### Class 08

[API Design Best Practices](https://docs.microsoft.com/en-us/azure/architecture/best-practices/api-design)

**What does REST stand for?**
Representational State Transfer


**REST APIs are designed around a ____.**
"resource" -- any kind of object, data or service that can be accessed by the client.



**What is an identifier of a resource? Give an example.**

a URI that uniquely identifies that resource. a customer order or request for information. 

**What are the most common HTTP verbs?**

GET, POST, PUT, PATCH, & DELETE

**What should the URIs be based on?**

Resource URIs should be based on the resource itself and not the methods or operations on the resource. 

**Give an example of a good URI.**

Something simple that can be flexible when the inventories and data in the backend change. Not too specific. 
like customer/1/orders could find all the orders for customer 1, and any other requests can be additional URIs

**What does it mean to have a ‘chatty’ web API? Is this a good or a bad thing?**

An API where there are too many small requests for smaller bits of information--generally not ideal. Try to design bigger resources that can be retrieved in a single request--if feasible. If it's too big, then it can increase the bandwidth cost and latency of a request. 

**What status code does a successful GET request return?**

200 OK

**What status code does an unsuccessful GET request return?**

if it is not found, it will be a 404. If it fulfilled the request but returned no content, then it is a 204.

**What status code does a successful POST request return?**

201-- content created. 

**What status code does a successful DELETE request return?**

204-- no content, it has been successfully handled. 


[RegExr Cheatsheet](https://regexr.com/)

[Regex Tutorial](https://medium.com/factory-mind/regex-tutorial-a-simple-cheatsheet-by-examples-649dc1c3f285)

[Regex 101](https://regex101.com/)


### Class 09


[Functional Programming Concepts](https://medium.com/the-renaissance-developer/concepts-of-functional-programming-in-javascript-6bc84220d2aa)

**What is functional programming?**

A style of building the structure of computer programs and elements that treats computing as evaluating functions and does not change state or data.

**What is a pure function and how do we know if something is a pure function?**
It returns the same result when given the same input. It does not rely on global objects that are not passed into it as params, it's more self-contained. It does not have a random internal generator within it. It will not modify any global obj or param passed by reference. 

**What are the benefits of a pure function?**

The outputs are predictable and the inputs are known. You can make exact predictive statements.

**What is immutability?**

Changing the value in stored in memory changes the memory itself. Immutability does not allow changes in the memory location. Strings are immuteable, so every time they are reassigned a different value, they are changing the memory state of that string. 

**What is Referential transparency?**

If two functions are given the same inputs, then they return the same result. So if they are pure functions, which work with immutable data, then they provide referential transparency. 

[Node JS Tutorial for Beginners #6 - Modules and require()](https://www.youtube.com/watch?v=xHLd36QoS4k)

**What is a module?**

Another js file with piece of code that has a certain functionality that we can then call upon when we need it. If we edit the modules, it makes it easier to expand and develop on the application in the future, because one file does not contain all functionality of the entire application. We can just change one part of that functionality in its self-contained module.  

**What does the word ‘require’ do?**

It calls the path to the module. 

**How do we bring another module into the file the we are working in?**

The method is not available to us outside the module so we need to bring it into the file.  We have to say exactly what part of the module we would like to use. 

**What do we have to do to make a module available?**

We need `require('./count');` in our main app file and set it equal to a variable like `var counter= require('./count');`, and then `module.exports = counter;` in our count.js module file. The exports part tells us what in our module is being made available when you call a file path to require it. Then you can call the variable `counter` in your app.js file to run that method as usual, like a method with params = `counter(['shuaun', 'blahh'])`

### Class 10

[Understanding the JavaScript Call Stack](https://medium.freecodecamp.org/understanding-the-javascript-call-stack-861e41ae61d4)

**What is a ‘call’?**

function invocation in javascript. It's done synchronously, one at a time, top to bottom of the code. 

**How many ‘calls’ can happen at once?**

one.

**What does LIFO mean?**

"It means that the last function that gets pushed into the stack is the first to be pop out, when the function returns."

**Draw an example of a call stack and the functions that would need to be invoked to generate that call stack.**
![IMG_9E001EFC658E-1](https://github.com/maddieamie/reading-notes/assets/118625447/2e1d40d9-1ea9-4bdc-a2a0-25b77b904183)


**What causes a Stack Overflow?**

A function that calls itself without an exit point. It runs until the browswer throws a Maximum call stack size exceeded, and thats the overflow.
Is that why they call the help forums that?

[JavaScript error messages](https://codeburst.io/javascript-error-messages-debugging-d23f84f0ae7c)

**What is a ‘reference error’?**

Variable is not yet defined or not defined in the proper way.

**What is a ‘syntax error’?**

When you use invalid or incorrect syntax, it can't be parsed.

**What is a ‘range error’?**

When an object's length is invalid when your code evokes it. 

**What is a ‘type error’?**

The type of thing you are trying to use is incompatible with how you are using it, or inaccessible.

**What is a breakpoint?**

A defined location in your code where it will stop running so you can examine what has happened until that point and what is being returned. 

**What does the word ‘debugger’ do in your code?**

It creates a breakpoint up until the point you define, stops executing at that line.

[JavaScript errors reference on MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors)
  
