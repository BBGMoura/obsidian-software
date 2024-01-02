### Use intention revealing names 
It should describe why it exists, what it does and how it is used. Example : `elapsedTimeInDays`.

### Avoid Disinformation
Avoid false clues that obscure the meaning of the code. For example, `hp`, `aix`, and `sco` would be poor variable names are they are names of Unix platforms.

Do not refer to a group of accounts as an `accountList`, if it is not a list.  Even if the container is a list, it is better not to encode the container type into the name.

### Make Meaningful Distinctions
Do not name variables simply to satisfy the compiler. Example: `a1`, `a2`, and `a3`.

Noise words are meaningless distinctions.  For example, `ProductInfo` or `ProductData` do not mean anything different, even if the words are different.

The word variable should never appear in a variable name. The word tbale should never appear in a table name.

Distinguish names in a way  the reader knows what the differences offer. This is a bad example:
``` java
getActiveAccount();
getActiveAccounts();
getActiveAccountInfo();
```

