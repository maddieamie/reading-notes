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


