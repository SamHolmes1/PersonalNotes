- Know what React is and why we would use it
- Understand the basic file structure of a React app
- know how to use JSX to create HTML elements
- know how to use JS expressions within JSX
- Know how to create functional componenets
- Be able to use props to pass information to a component

# React 101
- The library for web and native user interfaces
- Javascript library
- Built by facebook
- It's been around for 10 years
- Most widely used Front-End library
- Gentle learning curve
- Builds on familiarity with JS

# DOM vs React
## Dom
- Low level API provided by browsers
- Direct manipulation can be cumbersome 
- Imperative
- Direct DOM manipulation can be slow

## React
- High level library that provides abstraction
- Handles DOM updates for us
- Declarative
- Uses a virtual DOM which requires less direct manipulations

# Vite
 - Creates file structure and adds dependenceis
 - Parses the source code and transforms it into JS(esbuild)
 - Hot Module Replacement (change detection)

# Example
- Node is back
- The only things within the body is a div that has an id of "root" and a script tag.
- You can use a tool called esbuild in the browser to see how JSX will be converted to regular JS using the option os --loader="jsx"
- JSX stands for JavaScript XML
- html within jsx must be enclosed. so you can't have a h1 and a p tag on their own, you need something like a section or a div. A single p tag is fine though
- You can enclose multiple html tags in empty tags and it will remove them at render time and render both of those tags
- Expressions can be written into html using curly braces
- FUNCTIONAL COMPONENTS MUST BE IN UPPER CAMEL CASE

```jsx
//main.jsx
import ReactDOM from "react-dom/client"; // ES6 module syntax used in browsers

const doggos = ["obi", "mabel", "bouncer"];

const greeting = <div><h1>Hello {doggo} ^_^</h1></div>; // Javascript XML allows HTML-like code within JavaScript Code


const Sum = ({ num1, num2 }) => { // props is an object that is passed to the function
	return <p> {num1} + {num2} = {num1 + num2}</p>
}

const App = () => { // This is a react functional component
	const doggo = "obi"
	
	return (<div><h1>Hello {doggo} ^^</h1>
	        <Sum num1={1} num2={17} />
	        </div>); // Javascript XML allows HTML-like code within JavaScript Code
};


reactDOM.createRoot(document.getElementById("root")).render(<App />); // uses the ReactDOM library to render something in the DOM
```

```jsx
const newGreeting = ( 
	<div>
		<ul>
		  {doggos.map((doggo) => {
			  return <li key={doggo}>Hello {doggo}<\li> 
		  })}
		<\ul>
	<\div>
); 

```