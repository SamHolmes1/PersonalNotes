# Review day
- Array Methods, Closure, recursion and OOP review day topics that will be covered
- Sensible TDD patterns - IMPORTANT

- The new keyword is important


# Fourth Pillar of OOP
## Polymorpism
- We can treat an instance as if it is it's parents class

# Review 
## Four steps for creating a factor function
- Object instantiation
- Object decoration
- Attach methods
- Return the object


# Constructor functions
## New
- Create an object for us
- Automatically return that object
- bind "this" for us
- create a prototypal link for us
## Constructor function

```js
function Counter() { //nouns denote a constructor classes, only for people
	this.count = 0; // the new keyword binds the 'this' keyword
	Counter.prototype.increment = function () {this.count++;}
}

const myCounter = new Counter();
```

# Classes
- Classes are syntactic sugar
```js
class Counter {
	constructor(){
		this.count = 0;
	}
	
	incrementCount() {
		this.count++;
		return count;
	}
	
	getCOunt(){
		return this.count;
	}
}

const myCounter = new counter();

```


```js
class Animal{
	constructor(name, food){
		this.name = name;
		this.food = food
	}
}

class dog extends Animal{
	constructor(name, owner) {
		super(name, "treats") // latin for above, pass relevent args for parent
		this.owner = owner; 
	}
	
}
```