Python has a built in class named `str` with many features (there is an old module named `string` that should not be used). String literals can be enclosed by single or double quotes - single are more commonly used. 

Backslash escapes work the usual way within both single and double quoted literals -- e.g. `\n \' \"`. 

A string literal can span multiple lines but there must be a backslash `\` at the end of each line to escape the new line. 

String literals inside triple quotes """ or ''' can span multiple lines of text.

Python strings are `immutable` which means they cannot be changed after they are created (similar to Java). Since strings can't be changed, we construct new strings as we go.

``` python
# example
s = 'hello'
c = 'there'
# new string 'hellothere'
n = s + c
```

Characters in a string can be accessed using the standard [] syntax, and like Java and C++, Python uses zero-based indexing. Therefore, in string `s = hello`, `s[1] = e`.  If the index is out of bounds for the string, Python raises an error. 

The `len(string)` function returns the length of a string. The [] syntax and the `len()` function actually work on any sequence type - `strings, lists, etc.` Note : don't use `len` as a variable name to avoid blocking out the `len()` function.

The `+` operator can concatenate two strings.

``` python
s = 'hi'
s[1] # i
len(s) # 2
s + ' there' # hi there
```

Unlike Java, the `+` does not automatically convert numbers or other types to string form. The `str()` function converts values to a string form so they can be combined with other strings.

``` python
pi = 3.14
text = 'The value of pi is ' + str(pi)
```

