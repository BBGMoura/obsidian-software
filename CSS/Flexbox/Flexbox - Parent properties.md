This is a flexbox [cheatsheet](https://dev.to/simonpaix/css-flexbox-cheat-sheet-1g09).

## Parent properties

### Display

Enables flex container for all direct children. All children inside this container are now considered flex items.

``` css
.container{
	display: flex;
}
```

### Flex-direction

This sets the main axis of the container. There are four possible choices:
- row
- column
- row-reverse
- column-revers

``` css
.container{
	display: flex;
	flex-direction: collumn;
}
```

For example, collumn makes the main axis **vertical**. This means the children side the container will stack up.

### Justify-content 
This defines the alignment along the **main axis**. In the case where the direction is collumn, the main axis is **vertical**. In the case where the direction is row, the main axis is **horizontal**. The possible choices are:
- flex-start
- flex-end
- center
- space-between
- space-around
- space-evenly

```css
.container{
	display: flex;
	flex-direction: collumn;
	justify-content: space-around;
}
```

### Align-items
This defines the alignment along the **cross-axis**. n the case where the direction is collumn, the main axis is **horizontal**. In the case where the direction is row, the main axis is **vertical**. The possible choces are:
- flex-start
- flex-end
- center
- stretch
- baseline

```css
.container{
	display: flex;
	flex-direction: collumn;
	justify-content: space-around;
	align-items: center;
}
```

### Align-content 
This aligns multiple lines, like justify-content does with individual items. The possible choices are:
- flex-start
- flex-end
- center
- stretch
- space-between
- space-around

```css
.container{
	display: flex;
	flex-direction: collumn;
	align-content: stretch;
}
```