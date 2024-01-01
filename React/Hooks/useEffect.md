The useEffect hook lets you perform side effects in function components. Data fetching, setting up a subscription, and manually changing the DOM are examples of side effects.

## Effects without Cleanup

- Network requests
- manual DOM mutations
- logging

These are examples of effects that dont require cleanup.

### Classes Example
In class componenets, the render method itself should not cause side effects. Side effects should be put into componenetDidMount and componentDidUpdate.

`componetDidMount()` occurs when the component just mounted.

`componenetDidUpdate()` occurs when the component is updated.

## Hooks example

If you want something to occur on both instances, you have to define them in each of these functions. `useEffect()` gets rid of this issue. By default, `useEffect()` runs after every render.

## Effects with Cleanup
Clean up is needed to prevent memory leaks.

### Classes Example
 In React class, you should typically set up subscriptions in `componentDidMount()` and clean up in `componentWillUnmount()`.

### Hooks example

``` JS
import React, { useState, useEffect } from 'react';

function FriendStatus(props) {
  const [isOnline, setIsOnline] = useState(null);

  useEffect(() => {  
    
  function handleStatusChange(status) {      setIsOnline(status.isOnline);    }    ChatAPI.subscribeToFriendStatus(props.friend.id, handleStatusChange);   

// Specify how to clean up after this effect:

	return function cleanup() {      ChatAPI.unsubscribeFromFriendStatus(props.friend.id, handleStatusChange);    
	};  
});

  if (isOnline === null) {
    return 'Loading...';
  }
  return isOnline ? 'Online' : 'Offline';
}
```

# Dependency Array
https://codedamn.com/news/reactjs/useeffect-dependency
