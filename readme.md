# Immediately-Invoked Function Expression Discussion Questions

From Wikipedia: "An immediately-invoked function expression (or IIFE, pronounced 'iffy') is a JavaScript programming language idiom which produces a lexical scope using JavaScript's function scoping. Immediately-invoked function expressions can be used to avoid variable hoisting from within blocks, protect against polluting the global environment and simultaneously allow public access to methods while retaining privacy for variables defined within the function."

An IIFE can be useful for firing off a specific function one time in a specific place in your code, and can act as a shorthand version of defining and then calling a function separately.  IIFEs are similar to anonymous functions in the sense that they do not need to be declared with a name.

Immediately-invoked functions can be used in place of regular functions whenever you need the function to fire immediately after it's created.  They can keep your code a bit cleaner and more succinct, and can handle recursive functions and closures just fine.

*1. Paste the following code into your console and call 'fibonacciSeq()' a few times.  Discuss with your table what is happening in the following closure:*

```
var fibonacciSeq = (() => {
	let arr = [1,1]
	return () => {
		arr.push(arr[arr.length-2]+arr[arr.length-1])
		console.log(arr[arr.length-1])
	}
})()

fibonacciSeq()
fibonacciSeq()
fibonacciSeq()
```

---

*2. As a table, discuss how you could write and call the below function as a one line IIFE _without assigning the function to a variable_.  :*

```
function square(num) { return num*num}

square(5)
```

***Hint: you do not need to name the function.  You just need to declare it and pass in an argument immediately.***

---

*3. Here is the same function, but anonymous and written in arrow notation.  How would this be converted into an IIFE?  Again, do not assign it to a variable, it isn't necessary for immediately invoked expressions!*

```
var square = (num) => (num*num)

square(5)
```

---

*4. Final question - Write an IIFE that takes in two names, flips a 'coin' three times, and immediately returns the name that won the most games, along with the number of times that player won.*
