There are two ways to define a function:

- declaring a variable using `const`

``` JS
const doSomethingCool: string = () => 'yes'
```

- declaring using the `function` keyword

``` JS
function doSomethingCool(): string {
  return 'yes';
}
```


Pros of using `function` over `const`:
- Clear intent and it is more concise. Faster to see if it is a function or a variable.
- `Function` allows you to use function before you declare it due to function hoisting. `const` will leave it undefined until it's reached execution.
- Named functions show up in stack trace messages

Pros of using `const` over `function`:
- `const` prevents reassignment of the name while function does not.

