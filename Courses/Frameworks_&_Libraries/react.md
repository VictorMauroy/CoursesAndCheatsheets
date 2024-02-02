# Learning React

**Content:**
* [**JSX with React**](#jsx)
  - [What is JSX](#what-is-jsx)
  - [Tips](#tips)
  - [Warnings](#warnings)
  - [Useful links](#useful-links)

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