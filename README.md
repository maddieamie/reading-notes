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


  
