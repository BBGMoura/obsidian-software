#ReactV17
This is an old version of defining React components.

## Overview
To define a [React component](https://reactjs.org/docs/react-component.html) class, you need to extend React.Component:

``` javascript
class Welcome extends React.Component {
  render() {
    return <h1>Hello, {this.props.name}</h1>;
  }
}
```

React.Component is a JavaScript class. 

The only method that must be defined is render(). All other methods are optional.

## Component Lifecycle 
Each component has several “lifecycle methods” that you can override to run code at particular times in the process. This [diagram](https://projects.wojtekmaj.pl/react-lifecycle-methods-diagram/) explains this. 

### Mounting
These methodas are called in the following order when an isntanmce of a component is being created and inserted into the DOM:
- constructor()
- render()
- componentDidMount()
- componentDidUpdate()

### Unmounting 
This method is called when a component is being removed fromt he DOM:
- componentWillUnmount()

## Reference 

### render()

``` javascript
render()
```

The `render()` method is the only required method in a class component.

When called, it should examine `this.props` and `this.state` and return one of the following types:

- **React elements.** Typically created via JSX.
- **Arrays and fragments.** Let you return multiple elements from render.
- **Portals**. Let you render children into a different DOM subtree. 
- **String and numbers.** These are rendered as text nodes in the DOM.
- **Booleans or null or undefined.** Render nothing. (Usually for tests).

The `render()` function should be pure, meaning that it does not modify component state, it returns the same result each time it’s invoked, and it does not directly interact with the browser.

If you need to interact with the browser, perform your work in `componentDidMount()` or the other lifecycle methods instead. Keeping `render()` pure makes components easier to think about.

`render()` will not be invoked if `shouldComponentUpdate()` returns false.

When you pass the component `<Welcome />` to ReactDOM.render(), it will tell the welcome component to call it's Welcome.render() method. Therefore, all components need a render method.

### constructor()

``` javascript
constructor(props)
```

**If you don’t initialize state and you don’t bind methods, you don’t need to implement a constructor for your React component.**

The constructor for a React Component is called before it is mounted. When implementing the constructor for a React.Component subclass, you should call super(props) before any other statement. Otherwise, this.props will be undefined in the constructor, which can lead to bugs.

Typically, in React constructors are only used for two purposes:

- Initializing local state by assigning an object to this.state.
- Binding event handler methods to an instance.

You should not call setState() in the constructor(). INstead, if your component needs to use local state, assign the inital state to this.state dirertly in the constructor:

``` javascript
constructor(props) {
  super(props);
  // Don't call this.setState() here!
  this.state = { counter: 0 };
  this.handleClick = this.handleClick.bind(this);
}
```

You should only assign this.state in the constructor. In other methods, use this.setState() instead.

Avoid introducing side-effects or subscriptions in the constructor. For those cases, use componentDidMount() instead.

**NOTE**
Avoid copying state into state! This is a common mistake:
``` javascript
constructor(props) {
 super(props);
 // Don't do this!
 this.state = { color: props.color };
}
```

The problem with this is :
- It is unecessary. You access it with this.props.color directly.
- Creates bugs. Updates to the color prop won't be reflected in the state.

**Only use this pattern if you intentionally want to ignore prop updates.** In this case, it makes sense to rename the prop to be caussed defaultColor. You can then force a component to “reset” its internal state by [changing its `key`](https://reactjs.org/blog/2018/06/07/you-probably-dont-need-derived-state.html#recommendation-fully-uncontrolled-component-with-a-key) when necessary.

### componentDidMount()

```javascript
componentDidMount()
```

This function is evoked immediately after a component is mounted (inserted into the tree). Initialization that requires DOM nodes should go here. If you need to load data from a remote endpoint, this is a good place to instantiate the network request.

This method is a good place to set up any subscriptions. If you do that, don’t forget to unsubscribe in `componentWillUnmount()`.

You **may call `setState()` immediately** in `componentDidMount()`. It will trigger an extra rendering, but it will happen before the browser updates the screen. This guarantees that even though the `render()` will be called twice in this case, the user won’t see the intermediate state. Use this pattern with caution because it often causes performance issues. In most cases, you should be able to assign the initial state in the `constructor()` instead. It can, however, be necessary for cases like modals and tooltips when you need to measure a DOM node before rendering something that depends on its size or position.

### componentDidUpdate()

``` javascript
componentDidUpdate(prevProps, prevState, snapshot)
```

`componentDidUpdate()` is invoked immediately after updating occurs. This method is not called for the initial render.

Use this as an opportunity to operate on the DOM when the component has been updated. This is also a good place to do network requests as long as you compare the current props to previous props (e.g. a network request may not be necessary if the props have not changed).
``` javascript
componentDidUpdate(prevProps) {
  // Typical usage (don't forget to compare props):
  if (this.props.userID !== prevProps.userID) {
    this.fetchData(this.props.userID);
  }
}
```

You **may call `setState()` immediately** in `componentDidUpdate()` but note that **it must be wrapped in a condition** or you’ll cause an infinite loop. It would also cause an extra re-rendering which, while not visible to the user, can affect the component performance. If you’re trying to “mirror” some state to a prop coming from above, consider using the prop directly instead. Read more about [why copying props into state causes bugs](https://reactjs.org/blog/2018/06/07/you-probably-dont-need-derived-state.html).

**NOTE**
`componentDidUpdate()` will not be invoked if [`shouldComponentUpdate()`](https://reactjs.org/docs/react-component.html#shouldcomponentupdate) returns false.