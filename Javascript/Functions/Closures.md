A closure is created when a function is defined inside another function. The inner function references variables in the outer function's scope. **When the inner function is returned from the outer function, it retains a reference to the outer functions scope.** It can continue accessing those values even after the outer function has finished executing. The vice-versa is not true.

In other words, a closure can remember values from its outer function's scope and use them later even if the outer function has returned. 

## When to use a closure

- Can be used for the retrieval of dead values which have become out of scope. Also, it  can be used for privatising some variables or function.  
- Thus closures are useful for creating private variables and functions, implementing partial function application, and preserving state in asynchronous code.

## Where and How to use

1. Private variables and functions

``` JS
const makeCounter = () => {
	let count = 0;
	return () => {
		count++;
		console.log(count);
	}
}

let counter = makeCounter();
//call counter
counter(); // = 1
counter(); // = 2
counter(); // = 3
```

- In this example, `makeCounter` is an `arrow function` that returns another `arrow function`. The returned function increments a count variable each time it is called, and logs the new value of `count` to the console.
- When `makeCounter` is called, it creates a new scope with a `count` variable initialised to `0`. It then returns a **new arrow function that "closes over" this scope and increments the count variable each time it is called.**
- When we assign the returned arrow function to the counter variable, we create a closure that retains a reference to the count variable.
- Each time we call `counter()`, it increments the `count` variable and logs the new value to the console, because it is still "closing over" the original `count` variable in the outer function's scope.
- Thus because the `count` variable is not exposed outside of the returned object, it is effectively a private variable that can only be accessed or modified through the `makeCounter()` methods.

2. Partial Function 
``` JS
function add(x) { 
	return function(y) { 
		return x + y; 
	} 
} 
let add5 = add(5); 
console.log(add5(3)); // 8
```

- In this example, the `add()` function returns another function that takes a single argument and returns the `sum` of that argument and the `x` value from the outer function's scope.
- This allows us to "partially apply" the `add()` function by passing in an `x` value and getting back a new function that always adds that value to its argument.
- Thus we can then use the new function like any other function, passing in different `y` values as needed.
