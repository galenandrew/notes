# JavaScript's Difficult Concepts Explained
@author Jeff Carouth @jcarouth
@date 2013-06-29
@url joind.in/8684
@deck speakerdeck.com/jcaraouth

## Misc
- Wat? [link](http://destroyallsoftware.com/talks/wat)

## Scope (`vars` and `variables`)
**Global** and **Function**
- var keyord

### Takeaway & Tip
- always avoid using global variable inside of functions…use var.
- always declare variables at the top of the function

## Context (`this`)
- `this` inside of a function depends on how the function was invoked
```
magicCounter = {
	count: 0,
	increaseCounter: function() {
		this.count++;
	},
	decreaseCounter: function() {},
		this.count--;
	};
```

### Force context
- `.call()` and `.apply()`

### Takeaway & Tip
- The `this` keyword and the context of the function entirely depends on how the function was called.
- The default context will be the global context for functions invoked by name or variable name…
- Using `call()` and `apply()` gives you the control you might need over the context of an object…

## Objects & Prototype
- Everything in Javascript is an object (even string, e.g. string.lenght())
- Most simple object in js is the object literal `{}`

### Object Oriented Javascript / Prototype Chain (Javascript's complicated inheritance model)
- when creating a constructor function the *convention* is to use a capital first letter (e.g. `function Person() {}` to be used like `var a = new Person();`)
- Every object in javascript has a `prototype` property which resembles the base template/object
- adding a function/behavior/property to an Object's prototype applies it to every instantiated object in real time (e.g. adding arms to Person object)

### Inheritance
- `Developer.prototype = Object.create(Person.prototype);` - this allows Developer to inherit the Person object's prototype behaviors and functions

### Takeaway
- OO development in javascript requires an understanding of the prototype [link](http://crth.net/mdnoopjs)

## Further Reading
### Books
- Javascript: The Good Parts
- Javascript Patterns

### sites
- watchmecode.net [link](http://crth.net/jsfundamentals)

## Recap
1. Avoid using global vars inside function scope
2. Context and `this` depend on invocation
3. Default context is the global context
4. `.call()` and `.apply()` gives you control over the context
5. All `Objects` have a `prototype`

## Resources
- `JSLint` and `JSHint`