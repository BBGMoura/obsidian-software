useCallback returns a memoized callback function. In other words, thehook returns the same function instance between renderings. 

``` JS
import React, { useCallback } from 'react';

function MyComponent() {
	const handleClick = useCallback(() => {
		// handle the click event
	}, []);

return <MyChild onClick={handleClick} />;
}
```

Typically, when a compoenent re-renders, the reference to a function changes. The useCallback hook keeps the function reference the same, unless the variable/function in it's dependency array has changed.

This is useful when:
1. A functional component wrapped inside React.memo() accepts a function object as prop
2. When the function object is a dependency to other hooks eg. in useEffect.
3. When the function has internal state.


