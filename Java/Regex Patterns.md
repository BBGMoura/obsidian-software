Brackets are used to find a rage of characters

`[abc]` -> find one char from the options between the brackets
`[^abc]` -> find one character NOT between the brackets
`[0-9]` -> find one character from the range 0-9

### Metacharacters
Metacharacters are characters with special meaning:

`|` -> find a match for any of the patterns separated by `|`. example : cat|dog|fish
`.` -> find just one instance of any character
`^` -> finds a match as the beginning of a string. example : `^Hello`
`$` -> finds a match at the end of the string. example : `World$`
`\d` -> find a digit
`\s` -> find a whitespace character
`\b` -> find a match at the beginning of a word like this: `\bWORD` or at the end `WORD\b`
`\uxxxx` -> find the Unicode character specified by the hexadecimal number xxxx

### Quantifiers
`n+` -> matches a string which contains at least one n
`n*` -> Matches any string that contains zero or more occurrences of n
`n?` -> Matches any string that contains zero or one occurrences of n
`n{x}` -> Matches any string that contains a sequence of X n's
`n{x,y}` -> Matches any string that contains a sequence of X to Y n's
`n{x,}` -> Matches any string that contains a sequence of at least X n's

### Password Regex
```javascript
^(.{0,7}|[^0-9]*|[^A-Z]*|[^a-z]*|[a-zA-Z0-9]*)$
```

``` java
^(?=.*[a-z])(?=.*[A-Z])(?=.*\\d)(?=.*[@#$%^&+=]).{8,}$
```

