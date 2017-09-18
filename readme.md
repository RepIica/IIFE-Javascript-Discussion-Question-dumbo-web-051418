# Immediately-Invoked Function Expression Discussion Questions

From Wikipedia: "An immediately-invoked function expression (or IIFE, pronounced 'iffy') is a JavaScript programming language idiom which produces a lexical scope using JavaScript's function scoping. Immediately-invoked function expressions can be used to avoid variable hoisting from within blocks, protect against polluting the global environment and simultaneously allow public access to methods while retaining privacy for variables defined within the function."

An IIFE can be useful for firing off a specific function one time in a specific place in your code, and can act as a shorthand version of defining and then calling a function separately.  IIFEs are similar to anonymous functions in the sense that they do not need to be declared with a name.

As a table, discuss how you could write and call the following function as a one line IIFE:

```
function square(num) { return num*num}

square(5)

***(function (num) { return num*num})(5)
```

***Hint: you do not need to name the function, just define it and pass in the argument.***

Here is the same function, but anonymous and written in arrow notation.  How would this be converted into an IIFE?

```
var square = (num) => (num*num)

square(5)

***((num) => (num*num))(5)
```

Immediately-invoked functions can be used in place of functions whenever you need the function to fire immediately after it's created.  They can keep your code a bit cleaner and more succinct, and can handle recursive functions and closures just fine.

Paste the following code into your console and call 'fibonacciSeq()' a few times.  Discuss with your table what is happening in the following closure (don't sweat if you haven't covered closures just yet):

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

Final question - Write an IIFE that takes in two names, flips a 'coin' three times, and immediately returns the name that won the most games, along with the number of times that player won.

```
((name1, name2) => {
    let players = {[name1]:0, [name2]:0}
    for(let i = 0; i < 3; i++) {
      (Math.floor(Math.random() * 2) == 0) ? players[name1]++ : players[name2]++
    }
    let result = players[name1] > players[name2] ? name1 +" "+players[name1] : name2 +" "+players[name2]
    return result
})("Daniel","Terrance")
```
