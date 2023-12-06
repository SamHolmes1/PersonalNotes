- Look at working with forms in React
- Understand what a contorller component is and why it's necessary
- Set state across seperate components


- You can pass down your setState function to child components

```jsx
//MoveAdder.jsx

const MoveAdder = () => {}
	const[input, setInput] = useState("")
	
	const updateInput = (event) => {
		setInput(event.target.value)
	}
	const handleSubmit = (event) => {
		event.preventDefault();
		props.setMoves((currMoves) => {
			return [...currMoves {id: currMoves.length + 1, name: input}]
		})
		setInput("");	
	}
	return (
		<form>
			<label htmlFor="move-input"> What's your best move?
				<input type="text" palceholder="type your move!" id="move-input" 
					onChange={updateInput} value={input}/>
			</label>
			<button >Add!</button>
		</form>
	)
;
```