If you want to create a list of JSX elements, then .map() is often your best bet. 

``` JSX
const strings = ['Home', 'Shop', 'About Me'];  
  
const listItems = strings.map(string => <li>{string}</li>);  
  
<ul>{listItems}</ul>
```

However, returning JSX as a variable is not best practice. It is better to map the component in the return section. In addition, it is important to keep [[Keys]] in mind when creating these lists in react.
