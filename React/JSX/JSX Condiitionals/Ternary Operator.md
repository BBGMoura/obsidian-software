The ternary operator is the short syntax for an if statement. 

You write `x ? y : z`, where x, y, and z are all JavaScript expressions. When your code is executed, `x` is evaluated as either “truthy” or “falsy.” If `x` is truthy, then the entire ternary operator returns `y`. If `x` is falsy, then the entire ternary operator returns `z`.

``` JSX
const headline = (  
  <h1>  
    { age >= drinkingAge ? 'Buy Drink' : 'Do Teen Stuff' }  
  </h1>  
);
```

n the above example, if `age` is greater than or equal to `drinkingAge`, then `headline` will equal `<h1>Buy Drink</h1>`. Otherwise, `headline` will equal `<h1>Do Teen Stuff</h1>`.