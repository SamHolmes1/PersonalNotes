- A promise represents a placeholder for an async operating that hasn't completed yet, but is expected in the future
- Added to JS as part of ES6
- we still need to use promises

# Promises
- Promises have three states
	- Pending, Fulfilled and rejected; can only resolve to one.
- A promise is a native constuctor E.G
	- JSON:Date:Promise


## How can we use promises?
```js
const wwaitForPartyRings = () => {
	return new Promise((resolve, reject) => {
	setTimeout(() => {
		const shops = ['co-op', 'tesco', 'spar', 'sainsburys']
		const pickAShop = Math.ceil(Math.random() * 4) - 1;
		if(pickAShop < 2){
			resolve('Here\'s your party ring')
		}else{
			reject('Shop does not have party rings')
		}
	}, 1000)
})
}


waitForPartyRings().then((result) => {
	console.log(result)
	return WaitForPartyRings()
	
}).then((result2) => {
	console.log(result2)
})
.catch((err) => {
	console.log(err)
})


```

- .catch() always goes at the end