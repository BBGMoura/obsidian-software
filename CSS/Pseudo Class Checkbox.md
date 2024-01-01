Changing the colour of a checkbox requires a pseudo element. Here is an exampe:
```css
input {
  position: relative;
  cursor: pointer;
}

input:before {
  content: "";
  position: absolute;
  width: 16px;
  height: 16px;
  top: 0;
  left: 0;
  border: 1px solid #99AFC1;
  border-radius: 3px;
  padding: 1px;
  background-color: #FFFFFF;
}

input:checked:before {
  background-color: #00AEEF;
}

input:checked:after {
  content: "";
  display: block;
  width: 5px;
  height: 10px;
  border: solid white;
  border-width: 0 2px 2px 0;
  -webkit-transform: rotate(45deg);
  -ms-transform: rotate(45deg);
  transform: rotate(45deg);
  position: absolute;
  top: 2px;
  left: 6px;
}
```