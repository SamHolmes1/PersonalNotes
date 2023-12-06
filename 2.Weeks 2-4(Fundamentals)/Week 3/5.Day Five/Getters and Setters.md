```js
class Temperature{
#temperature; // Don't need let or const
	constructor(tempAsCelsius){
		this.#temperature = tempAsCelsius;
	}
	get celsius(){
		return this.#temperature;
	}
	set celsius(temp){
		this.#temperature = temp;
	}
}


const temp = new Temperature(16)
temp.celsius = 12; // setter
console.log(temp.celsius) // getter
```

# Accessor Functions(getters and setters)
- Used to gain access to a property on a class
## Getters
- GET a property
- takes no arguments
## Setters
- SET a property
- Takes one argument

These functions are not invoked like usual JS functions.