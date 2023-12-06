- Consider how we can connect APIs with our front end to hydrate ouir apps with data.
- Find out how we can hook into the React lifecycle to achieve the above
- Learn about useEffect, it's argumnets, and how and when it is run


# effect vs event
https://react.dev/learn/synchronizing-with-effects

```jsx
//...
	const [books, setBooks] = useState([]);
	const [isLoading, setIsLoading] = useState(true);


	useEffect(() => {
		fetch('https://www.googleapis.com/books/v1/volumes?=war').then((res) => {
			return res.json();
		}).then((parsedRes) => {
			setBooks(parsedRes.items)//Sets it to the new array.
			setIsLoading(false);
		})
	}, [])

	if(isLoading){return <h2>Loading...</h2>}
//...
```

