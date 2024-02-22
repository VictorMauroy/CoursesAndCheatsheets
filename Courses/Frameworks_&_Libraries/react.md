# Learning React

**Content:**
* [**JSX with React**](#jsx)
  - [What is JSX](#what-is-jsx)
  - [Tips](#tips)
  - [Warnings](#warnings)
  - [Useful links](#useful-links)
* [**Starting with React**](#starting-with-react)
  - [Imports](#imports)
  - [Important files](#important-files)
* [**React Components**](#react-components)
  - [What are they ?](#what-are-they)
  - [Example](#example)
  - [Warnings](#warnings)
  - [How to use Components](#how-to-use-components)
  - [Advanced Components tips](#advanced-components-tips)


## JSX

When working with React, you'll need to use a JSX syntax whenever you want to customize what you want to see.

Here is an example:
```jsx
const title = <h1>Hello there!</h1>;
``` 
The JSX code is the right part of the above line: `<h1>Hello there</h1>`. It is wrapped inside Javascript.

### What is JSX ?
> JSX is a **syntax extension** of JavaScript that combines the JavaScript and HTML-like syntax to provide highly functional, reusable markup. It’s used to create DOM elements which are then rendered in the React DOM.

> While not required in React, JSX provides a neat visual reqresentation of the application’s UI.

> A JavaScript file containing JSX will have to be compiled before it reaches a web browser.

*By Codecademy.*

### Tips

**1) JSX really is like html.**

You can add attributes to JSX, just like HTML:
```html
<a href='http://www.github.com'>Welcome to the Web</a>;
```
You can nest JSX elements: 
```jsx
(
    <a href="http://www.github.com">
        <span>Click here</span>
    </a>
)
```

**2) You can use javascript inside JSX code:**
<br> By using opening an closing curly braces.
```html
<p>{ Math.random() }</p>;
```

**3) Set attribute with javascript variables**
```js
let imgUrl = "./resources/thing.png"
const thingImg = <img src={imgUrl} />
```

**4) Loops and conditions**

You cannot insert `if` or `else` statements inside JSX code. You must do it in the javascript part of your code. Example:
- this **will not work**:
```jsx
const nb = Math.random();
let thingImg = (
  <img src={
    if(nb < 0.5) {
      /* Some url */
    } else {
      /* Another url */
    }
  } />
)
```
- this **will work**:
```js
const coinFace = Math.random();
if(nb < 0.5) {
  <img src={/* Some url */} />
} else {
  <img src={/* another url */} />
}
```

You can use **ternary operator** in JSX:
```jsx
<h1>{ !daytime ? "Have a nice day" : "Good night" }</h1>
```

You can also use the **&& operator** for quick condition check:
```jsx
<h1>{ studentNote > 15 && "Good work!" }</h1>
```
*Note: If the left operand equals true, then the right operand is returned. If the first one equals false, "false" will be returned.*

**5) Arrays**

A few examples about how to use arrays and lists in JSX to make some interesting things:
```jsx
const liArray = [
  <li>item 1</li>, 
  <li>item 2</li>, 
  <li>item 3</li>
];

<ul>{liArray}</ul>

// is equal to do:

<ul>
  <li>item 1</li>
  <li>item 2</li>
  <li>item 3</li>
</ul>
```

You can also do that:
```jsx
const colors = ['Red', 'Blue', 'Grey'];

const liArray = colors.map(color => <li>{color}</li>);

<ul>{liArray}</ul>
```

**6) Keep array element state and order in memory**

To do that, you will need a `key` attribute inside your jsx element.
```jsx 
const peopleList = people.map((person, i) => (
  <li key={'person_' + i}>{person}</li>
));

root.render(<ul>{peopleList}</ul>);
```
Is is useful to avoid having or list items shuffled or loose a particuliar state (like a checked box).


### Warnings

#### 1) Unique outermost element
A JSX element can only have one outermost element. You can do that:
```jsx
const paragraphs = (
    <div>
        <p>Things</p>
        <p>Other things</p>
    </div>
);
```
but not that:
```jsx
const paragraphs = (
    <p>Things</p>
    <p>Other things</p>
);
```
The first opening tag and the last opening tag must belong to the same JSX element.

As an other solution, you could use **React Fragments**.
```js
render() {
  return (
    <React.Fragment>
      <ChildA />
      <ChildB />
      <ChildC />
    </React.Fragment>
  );
}
```

#### 2) Altered attributes
The class attribute isn't the same in JSX:
<br />Html version ->
```html
<p class="small">Nevermind</p>
```
JSX version -> 
```jsx
<p className="small">Nevermind</p>
```

The for attribute isn't the same either:
From `for` to `htmlFor`

#### 3) Self closing tag
**In html**, you can write `<br />` and `<br>`. <br>
**In JSX**, you can write `<br />` but you **cannot** write `<br>`! 

### Alternative to JSX in React
In React, there is also a lot of methods to not use JSX. Sometimes, it can be much easier with those methods.
For instance, you can do that **without JSX**:
```js
import { createElement } from 'react';

function Greeting({ name }) {
  return createElement(
    'h1',
    { className: 'greeting' },
    'Hello ',
    createElement('i', null, name),
    '. Welcome!'
  );

  //Which is the same as the following:
  <h1>
    Hello <i>{name}</i>. Welcome!
  </h1>
}

export default function App() {
  return createElement(
    Greeting,
    { name: 'Taylor' }
  );
}
//Which will create that:
<Greeting name="Taylor />
```

Same result but **with JSX**:
```jsx
function Greeting({ name }) {
  return (
    <h1 className="greeting">
      Hello <i>{name}</i>. Welcome!
    </h1>
  );
}

export default function App() {
  return <Greeting name="Taylor" />;
}
```

Check that link for more informations about [createElement](https://react.dev/reference/react/createElement). The above examples are taken from that link.

**What is the difference ?**
> We would use React.createElement() instead of JSX when we do not want to set up compilation for our project, which the use of JSX requires!


### Useful links
- [JSX Cheatsheet](https://www.codecademy.com/learn/react-101/modules/react-101-jsx-u/cheatsheet)
- [JSX with React Syntax](https://www.codecademy.com/resources/docs/react/jsx)
- [Common events and components in React](https://react.dev/reference/react-dom/components/common#)


## Starting with React

### Imports
In order to use the React.js library, **you need to import a few things**:
- `import React from 'react';` will create a new object named `React` which will contains a lot of methods. To summerize, this is the main import that you will use.
- `import ReactDom from 'react-dom/client';` allows to interact with the DOM. The React object imported above cannot do it.

### Important files
React has **two core files**:
- `App.js` is the top-level of your application.
- `index.js` is the entry point.

For instance, you will **define some Components in App.js** and you will then need to **import them into index.js in order to render them**.


## React Components
### **What are they ?** <br>
> React component is a small, reusable chunk of code that is responsible for one job, which often involves rendering HTML and re-rendering it whenever some data changes. *Codecademy*

> It’s useful to think of components as smaller pieces of our interface. Combined, they are the building blocks that make up a React application. In a website, we can create a component for the search bar, another component for the navigation bar, and another component for the dashboard content itself. *Codecademy*

### **Example**
```jsx
import React from 'react';

function MyComponent() {
  return <h1>Hello, I'm a functional React Component!</h1>;
}

export default MyComponent;
```

### **Warnings**
- When declaring a new React Component, you should **name your function by using PascalCase**. If you don't, React will start looking for build-in components and return an error.

### How to use Components

> App.js
```jsx
import React from 'react';

function MyComponent()
{
  return <h1>Wanna make a component ?</h1>;
}

export default MyComponent;
```

> index.js
```jsx
import React from 'react';
import ReactDom from 'react-dom/client';

import MyComponent from './App';

<MyComponent />

// Or you can do the following if you want to insert other components in it

<MyComponent>
  <AnotherComponent />
</MyComponent>
```

That is how you can use your component. The thing is that you aren't rendering it in the browser yet. You will need to add a few lines inside `index.js`:

> index.js
```jsx
ReactDOM.createRoot(document.getElementById('app'));
```
- `document.getElementById('app')` returns a DOM element from **index.html**.
- `createRoot()` receives the DOM element as the first argument and creates a root for it.
- `createRoot()` returns a reference to the root container on which you can call methods like `.render()`.

After the root is created, all that’s left to do is call the .render() method on the returned root and display the React component like so:

```jsx
ReactDOM.createRoot(document.getElementById('app'))
  .render(<MyComponent />);
```

From here, React will display `<MyComponent />` in the root and make it appear on the screen.

In an application fully built with React, you will only need to do this once. Once this is set up, React will manage the DOM of your application, and any updates to the UI is taken care of efficiently. Adding more components should take place in your top-level `App.js` file.

*(The above paragraphs where taken from Codecademy.)*

#### **Render multiple components**
```jsx
ReactDOM.createRoot(document.getElementById('app'))
  .render(
    <React.Fragment>
      <MyComponent /> 
      <SayHello />
    </React.Fragment>
  );
```

#### **Using variables into Components**
```jsx
const cat = {
  catName : 'Kitty',
  src: 'https://cat.fr/cat-img',
  alt: 'A cat picture',
  width: '200px'
};

function ShowCat() {
  return (
    <div>
      <h3> His name is {cat.catName} </h3>
      <img 
        src= {cat.src}
        alt= {cat.alt}
        width= {cat.width}
      />
    </div>
  );
}
```

### Advanced Components tips

#### **Add Event Handler**
```jsx
function MyComponent(){
  function handleHover() {
    alert('You should stop hovering this!');
  }
  return <div onHover={handleHover}></div>;
}
```

#### **Define props** (alias properties)

Let's see a good example:

> People.js
```jsx
import React from 'react';

function ShowPeople(props) {
  if(props.isAdmin == true) {
    return (
      <div>
        <h2 id={props.titleid}> Hello ADMIN {props.name}!</h2>
        <p>What do you want to do today, boss ?</p>
        ...
      </div>
    );
  } else {
    return (
      <div>
        <h2 id={props.titleid}> Hello {props.name}!</h2>
        <p>What do you want to do, today ?</p>
        ...
      </div>
    );
  }
  
}

export default ShowPeople;
```

> App.js
```jsx
import React from 'react';
import ShowPeople from './ShowPeople';

function App() {
  return <ShowPeople name="John" titleid="redTitle" isAdmin={false}/>
}

export default App;
```

This is how you can send informations from one component to another. It helps to customize them.

**Adding properties to components seems like adding attributes to an html tag.**

The following code: `<ShowPeople name="John" />` will call `ShowPeople` and send it an object which looks like:
```js
{ 
  "name" = "John"
}
```

You can also send more complexe objects, such as arrays or entities:
```jsx
<ShowPeoples names={["John", "Louis", "Lisa"]} />
```

Note that the values that aren't of the type `string` must be passed between curly braces.

Alternatively, since `props` is an object, you can also use destructuring syntax like so:

```jsx
function Button({displayText}) {
  return <button>{displayText}</button>;
}
```
Where `displayText` is a property name that could have been contained inside props.

#### **Event handler as prop**
> DontClick.js
```jsx
function DontClick () {

  //This is a function that will works as an event
  function handleClick() {
    alert("I said to no click :(");
  }

  return <MyButton onClick={handleClick} />;
}
```
> MyButton.js
```jsx
function MyButton(props) {
  return (
    <button onClick={props.onClick}>
      Don't click me! It hurts.
    </button>
  );
}
```
Do not forget to add `props` inside the function paranthesis.

#### Choosing children elements position
When working with components, you can choose to add content between their opening `<MyButton>` and closing tags `<MyButton/>`. The thing is that sometimes, you will want to choose where you want it to render inside your component:

> List.js
```jsx
import React from 'react';

function List(props) {
  let titleText = `Favorite ${props.type}`;
  if (props.children instanceof Array) {
    titleText += 's';
  }
  return (
    <div>
      <h1>{titleText}</h1>
      <ul>{props.children}</ul>
    </div>
  );
}

export default List;
```

> App.js
```jsx
import React from 'react';
import List from './List';

function App() {
  return (
    <div>
      <List type='Living Musician'>
        <li>Sachiko M</li>
        <li>Harvey Sid Fisher</li>
      </List>
      <List type='Living Cat Musician'>
        <li>Nora the Piano Cat</li>
      </List>
    </div>
  );
}

export default App;
```

The code `props.children` allows you to everything that you added between your opening and closing tag. <br>
When there is only one element, it will be returned directly. Where there is more than one, you will get an array (allowing you to threat them individually).

#### Setting default values for props
There are three ways to set a default value for your properties:

1) Adding `YourFunctionName.defaultProps`
```jsx
function Example(props) {
  return <h1>{props.text}</h1>
}

Example.defaultProps = {
  text: 'This is default text',
};
```

2) Specify a default value **in the function definition**:
```jsx
function Example({text='This is default text'}) {
   return <h1>{text}</h1>
}
```

3) **Setting a constant for a specific value**:
```jsx
function Example(props) {
  const {text = 'This is default text'} = props;
  return <h1>{text}</h1>
}
```

## Debugging React

In case you need to debug your react app, I recommend checking that quick course : [React Developer Tools](https://www.codecademy.com/courses/react-101/informationals/ready-react-developer-tools) by Codecademy.

It explains how to use a chrome extension called "React Developer Tools" which **add new tabs in the Chome DevTools** (Where you can see the DOM, javascript console, etc.). You will then be able to inspect the components of your react app and edit them in live (temporary). There is also a Profiler tab.