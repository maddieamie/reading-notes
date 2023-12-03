# Reading Notes
Reading notes for Code Fellows 

# Code 301 - Intermediate Software Development

## Prework Notes

### ES6 Classes
Make your own Class! :card_file_box:
<img width="300" height="500" alt="ES6 Class Notes" src="https://github.com/maddieamie/reading-notes/assets/118625447/3ec64e8e-9aa4-4966-83e5-557bbba4a133">

> [!NOTE]
> This is just an example from school for us to reference, wahooo.


### CSS Selector Reference
[CSS Diner](https://flukeout.github.io/)

### Introduction to React and Components

### Things I want to know more about
forEach loop able to run if/else boolean stuff.
Can forEach loop run an amount of times outside of the length of the array it is iterating over?


## Module 1: React and other such business


### Class 01 Reading

[Component-Based Architecture](https://www.tutorialspoint.com/software_architecture_design/component_based_architecture.htm)

**What is a “component”?**

A component is a software object, intended to interact with other components, encapsulating certain functionality or a set of functionalities. Little thing that interacts with other things.

**What are the characteristics of a component?**

It can be reused over so we don't have to type over a million of the same things.
Easily replaced.
Can be used in multiple contexts.
Can be extended, using EXTENDS... in React.
Doesn't expose the inner bits of the code to the user.
Independent of other components. 

**What are the advantages of using component-based architecture?**

Easy to deploy new things without affecting the whole app.
Costs less to use things that already exist.
It's easier to use libaries of other code to create something. 
Easy to resuse components. 
Each component working on its own increases the reliability of the whole structure. 
Easy to update and maintain. 
Independent and flexible. 

[What is Props and How to Use it in React](https://itnext.io/what-is-props-and-how-to-use-it-in-react-da307f500da0#:~:text=“Props”%20is%20a%20special%20keyword,way%20from%20parent%20to%20child)

**What is “props” short for?**

"Properties" being used for passing data from one component to another.

**How are props used in React?**

Props are passed into components like function arguments
Props data is immutable (read-only)

**What is the flow of props?**

Props can only be passed to components in one way (parent to child)




### Class 02 Reading 

[React lifecycle](https://medium.com/@joshuablankenshipnola/react-component-lifecycle-events-cb77e670a093)

**Based off the diagram, what happens first, the ‘render’ or the ‘componentDidMount’?**

Render comes first.

**What is the very first thing to happen in the lifecycle of React?**

Mounting: ( Constructor, static getDerivedStateFromProps, render, componentDidMount, and UNSAFE_componentWillMount)

**Put the following things in the order that they happen:** 

constructor, render, React Updates, componentDidMount, componentWillUnmount

**What does componentDidMount do?**

"This method is invoked immediately after a component is mounted. If you need to load anything using a network request or initialize the DOM, it should go here. This method is a good place to set up any subscriptions. If you do that, don’t forget to unsubscribe in componentWillUnmount().
setState() can be called here, but it should be used sparingly, because it will cause a rerender, which can lead to perfomance issues." [Quote from section here](https://medium.com/@joshuablankenshipnola/react-component-lifecycle-events-cb77e670a093)

**Video Notes**

[React State Vs Props](https://www.youtube.com/watch?v=IYvD9oBCuJI)

**What types of things can you pass in the props?**

They function kind of like function arguments. Types of things: tiles and subtitles, initial count of a counter, data in general that we want the components to update as we pass it through.

**What is the big difference between props and state?**

State is handled inside a component and props is handled on the outside (what we are passing into the component from the outside). We use props instead of just basic data so that the data can be updated without hard coding all of it.

**When do we re-render our application?**

When you change the state in your component, it re-renders that part of your application.

**What are some examples of things that we could store in state?**

When you need to update and rerender your application based on something the user has done. 
Using a counter, like in our Favorites part of our lab, based on user clicking it. 
When a user updates a form by clicking things or typing, those changes are stored in state. 




### Class 03 Reading

[React Docs - lists and keys](https://reactjs.org/docs/lists-and-keys.html)

**What does .map() return?**
It returns _"a new array populated with the results of calling a provided function on every element in the calling array."_ [quote](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/map)

**If I want to loop through an array and display each value in JSX, how do I do that in React?**
You can use curly braces `{}`

Ex from documentation:
```
const numbers = [1, 2, 3, 4, 5];
const listItems = numbers.map((number) =>
  <li>{number}</li>
);
```

and then you call it as an unordered list using the `{}` here:

```
<ul>{listItems}</ul>
```

**Each list item needs a unique ____.**
key.

**What is the purpose of a key?**
"Keys help React identify which items have changed, are added, or are removed." The "best way" is to use keys that are uniquely identifiable as list items in relation to their siblings, which they used in the example of data being provided.

Assigns a key as it is created.
```
const numbers = [1, 2, 3, 4, 5];
const listItems = numbers.map((number) =>
  <li key={number.toString()}>
    {number}
  </li>
);
```

Using a part of the data provided to use as a key. 
```
const todoItems = todos.map((todo) =>
  <li key={todo.id}>
    {todo.text}
  </li>
);
```

Use index as a last resort.
```
const todoItems = todos.map((todo, index) =>
  // Only do this if items have no stable IDs
  <li key={index}>
    {todo.text}
  </li>
);
```

[The Spread Operator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Spread_syntax)

**What is the spread (...) operator?**

"Spread syntax "expands" an array into its elements, while rest syntax collects multiple elements and "condenses" them into a single element." quote from documentation.

Syntax:

```
myFunction(a, ...iterableObj, b)
[1, ...iterableObj, '4', 'five', 6]
{ ...obj, key: 'value' }
```

**List 4 things that the spread operator can do.**

+ arrays can be spread into objects
  
```
const array = [1, 2, 3];
const obj = { ...array }; // { 0: 1, 1: 2, 2: 3 }
```

+ all primitives can be spread in objects
  
```
const obj = { ...true, ..."test", ...10 };
// { '0': 't', '1': 'e', '2': 's', '3': 't' }
```

+ You can call a constructor with `new` directly on an array by using spread syntax

```
const dateFields = [1970, 0, 1]; // 1 Jan 1970
const d = new Date(...dateFields);
```
+ More powerful array literal (create a new array using an existing array as one part of it)

```
const parts = ["shoulders", "knees"];
const lyrics = ["head", ...parts, "and", "toes"];
//  ["head", "shoulders", "knees", "and", "toes"]
```

**Give an example of using the spread operator to combine two arrays.**

Can also use the `.concat()` operator, like `arr1 = arr1.concat(arr2);`

```
let arr1 = [0, 1, 2];
const arr2 = [3, 4, 5];

arr1 = [...arr1, ...arr2];
// arr1 is now [0, 1, 2, 3, 4, 5]
```

**Give an example of using the spread operator to add a new item to an array.**

May be a little faster than using `.push()`?
```
var params = [ "hello", true, 7 ]
var other = [ 1, 2, ...params ]
```

**Give an example of using the spread operator to combine two objects into one.**

```
const obj1 = { foo: "bar", x: 42 };
const obj2 = { bar: "baz", y: 13 };

const mergedObj = { ...obj1, ...obj2 };
// { foo: "bar", x: 42, bar: "baz", y: 13 }
```


**Videos**
[How to Pass Functions Between Components](https://www.youtube.com/watch?v=c05OL7XbwXU)

**In the video, what is the first step that the developer does to pass functions between components?**

He passes the name of the function into the child component that is trying to update the state of the parent function from inside itsself. 

**In your own words, what does the increment function do?**

It increases the count of something by one when called.

**How can you pass a method from a parent component into a child component?**

`increment={this.increment}` into the `render` part of the parent app. 
```
render () {
return ( <App
        increment={this.increment}
          />
)
}
```

**How does the child component invoke a method that was passed to it from a parent component?**

<img width="365" alt="notes for reading 04" src="https://github.com/maddieamie/reading-notes/assets/118625447/6e13c971-8cbc-4a21-bde3-1ab0eaef4c73">


### Class 04 Reading

[React Docs - Forms] (https://reactjs.org/docs/forms.html)

**What is a ‘Controlled Component’?**

When React controls what happens to the form after subsequent user input and what happens when the form submits. The form's value is controlled by React instead of the rendered HTML. The input's value is tied to React's state. "`<input type="text">`, `<textarea>`, and `<select>` all work very similarly - they all accept a value attribute that you can use to implement a controlled component."

**Should we wait to store the users responses from the form into state when they submit the form OR should we update the state with their responses as soon as they enter them? Why.**

I think we should update the state as they are typing it in so that a. it updates the state of what is rendering back to the user and b. they don't lose all their stuff if the page has to reload. 

**How do we target what the user is entering if we have an event handler on an input field?**

`this.state.value` like in this example:

```
Name:
          <input type="text" value={this.state.value} onChange={this.handleChange} />
```


[The Conditional (Ternary) Operator Explained](https://codeburst.io/javascript-the-conditional-ternary-operator-explained-cac7218beeff)

**Written definitions & examples so I can actually memorize it instead of constantly looking it up**

If/else statement:
```
if ( condition ) {
  value if true;
} else {
  value if false;
}
```

Ternary operator:
```
condition ? value if true : value if false
```

+ The condition is what you’re actually testing. The result of your condition should be true or false or at least coerce to either boolean value.
+ A ? separates our conditional from our true value. Anything between the ? and the : is what is executed if the condition evaluates to true.
+ Finally a : colon. If your condition evaluates to false, any code after the colon is executed.

_Multiple Operator examples_

```let isStudent = true;
let price = 12;
isStudent ? (
  price = 8,
  alert('Please check for student ID')
) : (
  alert('Enjoy the movie')
);
```
+ checks if `isStudent` is true or false as a condition
+ it is true, so the one right after the `?` is executed to adjust price and send alert
+ if it _was_ false, then the block after the `:` would be executed

**Why would we use a ternary operator?**

To shorten your code and save time, I assume.

**Rewrite the following statement using a ternary statement:**

Original: 
```
if(x===y){
  console.log(true);
} else {
  console.log(false);
}
```

Rewrite:
```
x===y ? console.log(true) : console.log(false)
```



### Class 05 Reading

[React Docs - Thinking in React](https://reactjs.org/docs/thinking-in-react.html)

**General Notes**
_Step one:  Break the UI into a component hierarchy_
+ Start by drawing boxes around every component and subcomponent in the mockup and naming them.
+ Separate your UI into components, where each component matches one piece of your data model.
+ <img width="508" alt="React Component Structure Notes" src="https://github.com/maddieamie/reading-notes/assets/118625447/11f28488-f67d-477a-ae63-312de4b8fcc7">
+ Arrange them into a hierarchy. FilterableProductTable => {SearchBar, ProductTable} => {ProductCategoryRow, ProductRow}

_Step two:  Build a static version in React_
+ To build a static version of your app that renders your data model, you’ll want to build components that reuse other components and pass data using props.
+ Save state for later in the interactivity part.
+ You can either build “top down” by starting with building the components higher up in the hierarchy (like FilterableProductTable) or “bottom up” by working from components lower down (like ProductRow). In simpler examples, it’s usually easier to go top-down, and on larger projects, it’s easier to go bottom-up.
  
_Step three: Find the minimal but complete representation of UI state_
+ The most important principle for structuring state is to keep it DRY (Don’t Repeat Yourself). Figure out the absolute minimal representation of the state your application needs and compute everything else on-demand.
+ The filtered list of products isn’t state because it can be computed by taking the original list of products and filtering it according to the search text and value of the checkbox.
+ Things that remain unchanged over time, that are passed from a parent as props, and that are computed based on existing state/props are _NOT state_.
  
_Step four: Identify where your state should live_
+ you need to identify which component is responsible for changing this state, or _owns_ the state.
+ Decided where to put the state based on the steps below in the last note question.
  
_Step five: Add inverse data flow_
+  the form components deep in the hierarchy need to update the state in the parent.
+  [Deep Dive on Adding Interactivity](https://react.dev/learn/adding-interactivity)

**What is the `single responsibility principle` and how does it apply to components?**

A component should ideally only do one thing. If it ends up growing, it should be decomposed into smaller subcomponents.

**What does it mean to build a ‘static’ version of your application?**

You're building the outline of the hierarchy of components, their code, and then also what each component does without interactivity. Layout the functions and data as well.

**Once you have a static application, what do you need to add?**

You need to add the State, or the interactivity, into your application. 

**What are the three questions you can ask to determine if something is state?**

Which of these are state? Identify the ones that are not:

1. Does it remain unchanged over time? If so, it isn’t state.
2. Is it passed in from a parent via props? If so, it isn’t state.
3. Can you compute it based on existing state or props in your component? If so, it definitely isn’t state!

**How can you identify where state needs to live?**

Follow the steps:
1. Identify every component that renders something based on that state.
2. Find their closest common parent component—a component above them all in the hierarchy.
3. Decide where the state should live:
  a. Often, you can put the state directly into their common parent.
  b. You can also put the state into some component above their common parent.
  c. If you can’t find a component where it makes sense to own the state, create a new component solely for holding the state and add it somewhere in the hierarchy above the common parent component.



[Higher-Order Functions](https://eloquentjavascript.net/05_higher_order.html#h_xxCc98lOBK)

**What is a “higher-order function”?**

It passes another function as an argument, or returns another function.

**Explore the `greaterThan` function as defined in the reading. In your own words, what is line 2 of this function doing?**

In line 02, the function `greaterThan` is creating a function that takes in m as a parameter and compares it to the argument of n that is passed into the OC `greaterThan` function. The `greaterThan` higher-order function is determining what value you are comparing it to, and returns a function where you can compare a new value to the original parameter of `n`. 

```
function greaterThan(n) {
  return m => m > n;
}
let greaterThan10 = greaterThan(10);
console.log(greaterThan10(11));
// → true
```

**Explain how either `map` or `reduce` operates, with regards to higher-order functions.**

`map` : transforms an array of data passed into it and creates a new array of data with what was transformed.

```
function map(array, transform) {
  let mapped = [];
  for (let element of array) {
    mapped.push(transform(element));
  }
  return mapped;
}
```

`reduce`: 
+ You end up with 1 value by repeatedly taking a single element from the array and combining it with the current value.
+ The parameters to reduce are, apart from the array, a combining function and a start value. i.e. `(array, combine func, starting value)`
+ If your array parameter contains at least 1 element, you don't need the starting value param. It will take the first element of the array as its start value and start reducing at the second element.
  
```
function reduce(array, combine, start) {
  let current = start;
  for (let element of array) {
    current = combine(current, element);
  }
  return current;
}

console.log(reduce([1, 2, 3, 4], (a, b) => a + b, 0));
// → 10
```

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
  
## Module 3

### Class 11

[nosql vs sql](https://www.thegeekstuff.com/2014/01/sql-vs-nosql-db/?utm_source=tuicool)

1. Fill in the chart below with five differences between SQL and NoSQL databases:

SQL: relational database // table based, schema that is predefined, vertically scalable by increasing hardware,
structured query language for defining and manipulating data. 

NoSQL: non-relational // document based, key-value pairs, graphs, or wide-column, no standard schema (dynamic schema for 
unstructured data), horizontally scalable by increasing servers to reduce load, queries are focused on a collection of documents with syntax that 
varies from database to database 


   1. What kind of data is a good fit for an SQL database?
  a complex query intensive environment with a need for power, and heavy duty transactional type applications 
   
1. Give a real world example.
My SQL database. 
   
1. What kind of data is a good fit a NoSQL database?
  they fit better for a hierarchical data storage with key-value pairs, similar to JSON data. Highly preferred for large data sets. Hbase is an example. 
   
1. Give a real world example.
Mongo DB
   
1. Which type of database is best for hierarchical data storage?
NoSQL
   
1. Which type of database is best for scalability?
SQL

[sql vs nosql](https://www.youtube.com/watch?v=ZS_kXvOeQ5Y)(Video)

  1. What does SQL stand for?
structured query language 

  1. What is a relational database?
Works with tables and has a clear schema that we can call and update. 
Joins retrieve related data

  1. What type of structure does a relational database work with?
It can't add more than is defined for the table of data
All records follow a schema
Work with related multiple tables -- set up the relations between the tables


  1. What is a 'schema'?
It defines the type of data for a relational database-- the organization and logic
of your data within the database. 

  1. What is a NoSQL database?
Able to store lots of data in an efficient way. 
You don't have to use the same schema for document type data 


  1. How does it work?
Generally there are no relations, though you could set them up. 
You store infomation in collections.
Have less time taken for relational querying but then you have to update multiple
collections at once. 

  1. What is inside of a MongoDB database?
  1. Which is more flexible - SQL or MongoDB? and why.
MongoDB is more flexible because you can hold multiple types of data. 

  1. What is the disadvantage of a NoSQL database?
They don't support ACID (atomicity, consistency, isolation, durability)

 Bookmark and Review

- [mongoose api](https://mongoosejs.com/docs/api.html#Model)
- [React Router](https://reactrouter.com/web/api/BrowserRouter)


### Class 12

[Status Codes Based On REST Methods](https://www.moesif.com/blog/technical/api-design/Which-HTTP-Status-Code-To-Use-For-Every-CRUD-App/)

1. In your own words, describe what each group of status code represents:

   - 100's = informational status codes that tell us what's happening in requests
   - 200's = a request was successfully made, but that doesn't mean it fully processed successfully
   - 300's = redirect codes -- tells the client that what they were looking for isn't where they were looking for it anymore
   - 400's = client error codes --" timeouts, wrong URI, missing authentication, etc. A client is sending incorrect input and should confirm the input parameters are correct before retrying the request."
   - 500's = server error codes, usually best for client to retry their request

1. What is a status code 202?
   something was created! Should return a location header with a url
   
1. What is a status code 308?
   Permanent Redirect: This tells the client to use another URL to access the resource and not use the current URL anymore.
   
1. What code would you use if an update didn't return data to a client?
    No Content - A proper code for updates that don’t return data to the client, for example when just saving a currently edited document.
   
1. What code would you use if a resource used to exist but no longer does?
   410 Gone - This is like 404 but we know that the resource existed in the past, but it got deleted or somehow moved, and we don’t know where.
   
1. What is the 'Forbidden' status code?
   403 Forbidden - The client has authorized or doesn’t need to authorize itself, but still has no permissions to access the resource.

[Build A REST API With Node.js, Express, & MongoDB - Quick](https://www.youtube.com/channel/UCFbNIlppjAuEX4znoulh0Cw) - First 20 minutes

1. Why do we need to pull our MongoDB database string out of our server and put it into our .env?
    process.env.VARIABLE  and do require('dotenv').config();
     
1. What is middleware?
Code that runs when the server gets a request but before it gets to your routes.
   
1. What does `app.use(express.json())` do?
It requires us to use express as our middleware software. It allows us to accept json as a body.
   
1. What does the `/:id` mean in a route?
   It is a parameter with a colon, and the id is the specific thing.
   
1. What is the difference between `PUT` and `PATCH`?
    Patch: only updates based on what the user passes to us.
   Put: It updates all the information about the subscriber at once. 
1. How do you make a default value in a schema?
   default: Date.now
1. What does a `500` error status code mean?
   Internal server error: actual server had an error, it doesn't
1. What is the difference between a status `200` and a status `201`? 200: ok, 201: ok, something was created.

### Class 13

[CRUD Basics](https://medium.com/geekculture/crud-operations-explained-2a44096e9c88)

   1. Which HTTP method would you use to update a record through an API?
      PUT
      
   1. Which REST methods require an ID parameter?
      PUT & DELETE

[Speed Coding: Building a CRUD API](https://www.youtube.com/watch?v=EzNcBhSv1Wo)

  1. What's the relationship between REST and CRUD?
  1. If you had to describe the process of creating a RESTful API in 5 steps, what would they be?

### Class 15

- [What is OAuth](https://www.csoonline.com/article/3216404/what-is-oauth-how-the-open-authorization-framework-works.html)

  1. What is OAuth?
     OAuth is an open-standard authorization protocol or framework that describes how unrelated servers and services can safely allow authenticated access to their assets without actually sharing the initial, related, single logon credential.
     
  1. Give an example of what using OAuth would look like.
  Auth0 allows a user to log into a new website using their login credentials from a previous thing they are already signed into. They may have to approve the new site's ability to access user info, but then they can use that app using other credentials they already have.

  1. How does OAuth work? What are the steps that it takes to authenticate the user?
    1. The first website's user info connects to the second website using Auth0's verified identity from the first one.
    2. Second website using Auth0 creates a request token & secret for a one-time transaction.
    3. The token and secret are given to initate the user's client software from first site.
    4. Client's software presents it to authorization provider.
    5. Client is asked to authenticate and approve the authorization transaction.
    6. The user approves (or their software silently approves) a particular transaction type at the first website.
    7. The user is given an approved access token (notice it’s no longer a request token).
    8. The user gives the approved access token to the first website.
    9. The first website gives the access token to the second website as proof of authentication on behalf of the user.
    10. The second website lets the first website access their site on behalf of the user.
    11. The user sees a successfully completed transaction occurring.


  1. What is OpenID?
     It uses authentication instead of authorization methods-- you need to prove you're human, hurrah. " In 2014, OpenID Connect was released, which reinvented OpenID as an authentication layer for OAuth. In this space, OpenID has found a niche, and the two technologies now complement each other in many implementations."

- [Authorization and Authentication flows](https://auth0.com/docs/flows)

  1. What is the difference between authorization and authentication?
     Authorization allows a machine to log you in using previously allowed services to communicate with a new website.
     Authentication requires you to prove that you are a user and you are who you say you are. 
     
  1. What is Authorization Code Flow?
     ![Authorization Code Flow](https://images.ctfassets.net/cdy7uua7fh8z/2nbNztohyR7uMcZmnUt0VU/2c017d2a2a2cdd80f097554d33ff72dd/auth-sequence-auth-code.png)
     
  1. What is Authorization Code Flow with Proof Key for Code Exchange (PKCE)?
     ![Proof Key Diagram](https://images.ctfassets.net/cdy7uua7fh8z/3pstjSYx3YNSiJQnwKZvm5/33c941faf2e0c434a9ab1f0f3a06e13a/auth-sequence-auth-code-pkce.png)
     
  1. What is Implicit Flow with Form Post?
     ![Implicit Flow](https://images.ctfassets.net/cdy7uua7fh8z/6m0uE4E7Hpzbdhyh9dEuYK/e36c910ff47a7540bf27e23c02822624/auth-sequence-implicit-form-post.png)
     
  1. What is Client Credentials Flow?
     ![Client Credentials](https://images.ctfassets.net/cdy7uua7fh8z/2waLvaQdM5Fl5ZN5xUrF2F/326677a1322f7fadeaffd9a32777824a/2023-09-22_11-06-54.png)
     
  1. What is Device Authorization Flow?
     ![Device Authorization](https://images.ctfassets.net/cdy7uua7fh8z/1A6jpG3W1H6SC9ZK92NyKd/40af53209f90a7c392f621f329fb4424/auth-sequence-device-auth.png)
     
  1. What is Resource Owner Password Flow?
     ![Resource Owner](https://images.ctfassets.net/cdy7uua7fh8z/4EeYNcnVX1RFcTy5z4lP4v/c3e4d22e6f8bf558caf07338a7388097/ROP_Grant.png)

Bookmark and Review

- [Auth0 for single page apps](https://auth0.com/docs/libraries/auth0-react)
