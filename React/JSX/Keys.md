When you make lists in JSX, sometimes you will need to include keys.

A `key` is a JSX attribute. The attribute’s _name_ is `key`. The attribute’s _value_ should be something unique, similar to an `id` attribute. These are used internally to track list order by React.

A list needs keys if either of the following are true;
 - The list-items have _memory_ from one render to the next. For example, in a checklist to-do list, each time must "remember" if it has been checked off.
- A list order might be shuffled. For example, a list of search results.

If neither of these conditions are true, then you don’t have to worry about `keys`. If you aren’t sure then it never hurts to use them!

### What should a key's value be?

Each key must be a unique string that React can use. If ypu are using `.map()`, you can add i parameter to access each elemnet's unique index:

``` JSX
const peopleLis = people.map((person, i) =>

// expression goes here:

<li key={'person_' + i}>{person}</li>

);
```
