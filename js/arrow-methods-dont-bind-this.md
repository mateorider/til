# ES6 Arrow Functions as Methods Don't Bind to `this`
## April 26, 2021

When adding methods to an object, I need to use the correct function syntax if for some reason I need access to the object's `this`.

Take this object for example:
```javascript
const person = {
	name: "Jon"
}
```

Let's say I wanted to add a `greet()` method to the object that simply printed "Hi, I'm Jon"

If I defined the method using arrow syntax, I would not be able to use `this.name` to get the name value. 
```javascript
const person = {
	name: "Jon"
	greet: () => {
		console.log(`Hi, I'm ${this.name}`)
	} 
}

person.greet() // "Hi, I'm undefined"
```

If I need access to `this`, I should use the normal `function` syntax to declare the method.
```javascript
const person = {
	name: "Jon"
	greet: function() {
		console.log(`Hi, I'm ${this.name}`)
	} 
}

person.greet() // "Hi, I'm Jon"
```

The other alternative is to use the newer, cooler, and more concise *ES6 Method Syntax* 
```javascript
const person = {
	name: "Jon"
	greet() {
		console.log(`Hi, I'm ${this.name}`)
	} 
}

person.greet() // "Hi, I'm Jon"
```

So arrow functions do not bind their own `this` value, making them poor candidates for methods but great for everything else.
