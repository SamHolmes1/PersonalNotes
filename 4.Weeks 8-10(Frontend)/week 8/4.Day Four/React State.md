- Learn how to setup new Reaect projects

# VIte
- Vite is a tool that allows us to create React apps much easier
```bash
npm create vite@latest
Project-name: My Project
select a framework: React
Select a variant: Javascript
Done.
cd My\ Project
npm install
npm run dev
```
- Only include files where you know what they're doing and you need them 
- Within the HTML, you only have a root div and a script importing main.jsx
- React.StrictMode is a strict way of running react, stringent rules for running code
- ^ for first timers it might be better to remove it
- Don't touch vite.config.js it tells vite that we're using react


# React State
- What is state?
- How to keep track of changes in our Apps(state)
- How to update state in event handlers
- Keeping state updates pure#
## Examples of state
- Upvotes: 1.6k
- UnreadPosts: \[post1, post2, post3, post4]
- profile{
	name: "sam",
	isActive: true,
	status: "in meeting"
}

## App flow
- This is a typical order of execution
Reading Variables -> Rendering components/ page -> updating variables
- React order of execution
Reading vars -> Render components -> update vars -> setState()

```jsx
//App.jsx
import Counter from '../components/Counter'
function App(){
	return ()
}

export default App;
```

- usestate() returns an array containing a value and a function.

```jsx
// /components/Counter.jsx

const Counter = () => {
	const [count, setCount] = useState(0); // Array destructuring since useState()        returns an array containing a value and a function to update the value

	function updateCount(inc) {
		setCount((currentCount) => {
			return currentCount + inc
		})
	}

	return (
		<div>
			<h1>my Counter</h1>
			<p>count: {count}</p>
			<button onClick={() => {
				updateCount(5);
				updateCount(5)
			}}>Click me!</button>
		</div>
	);
}

export default Counter;
```

```jsx

const ToDos = () => {
	const [todos, setTodos] = useState([
		{
			id: 1,
			task: "day 1"
		},
		{
			id: 2,
			task: "day 2"
		}
	])

	function addToDo() {
		setTodos((currentTodos) => {
		
		const newTodo = { id: currTodos.length + 1, task: `day ${currTodos.length + 
		1}`};
		const updatedTodos = [..currentTodos];
		updatedTodos.push(newTodo);
		return updatedTodos;
		
		})
	}
}
```

- React changes state by creating a new snapshot of the html and only changes the things that are different
- state++ isn't great as it reassigns the variable, you should use state + 1.
- setState is an async function, so multiple calls in the same block won't work or maybe display undefined behaviour
- setState can take a callback function that takes the current state as an argument. This will be a synchronous function