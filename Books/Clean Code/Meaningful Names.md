### Use intention revealing names 
It should describe why it exists, what it does and how it is used. Example : `elapsedTimeInDays`.

### Avoid Disinformation
Avoid false clues that obscure the meaning of the code. For example, `hp`, `aix`, and `sco` would be poor variable names are they are names of Unix platforms.

Do not refer to a group of accounts as an `accountList`, if it is not a list.  Even if the container is a list, it is better not to encode the container type into the name.

Be aware of names which vary in small ways. 

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

### Use Pronounceable Names
Simple. Use pronounceable names.

### Use Searchable Names
Single-letter names and numeric constants are not easy to locate across a bod of text. 

It is easier to search for `MAX_CLASSES_PER_STUDENT` than the number 7. 

Like wise names like `e` is a poor choice for a variable as it is hard to search for. 

Single-letter names can ONLY be used as local variables inside short methods. The length of the name should correspond to the size of the scope. 

### Avoid Encoding
Encoding type or scope information into names adds an extra burden of deciphering.

### Hungarian Notation
Do not include type into name. For example, `String phoneString`, if this type then changes, we have a problem: `PhoneNumber phoneString`.

### Member Prefixes
You do not need to prefix member variables anymore. Member variables are variables which belong to a class. We do not need `m_variable` anymore. 

Your classes and functions should be small enough to not need these. 

This turns into unseen clutter as people eventually ignore the `m_`. 

### Interfaces and Implementation
These can be a special case for encoding. For example, if you are building an ABSTRACT FACTORY for the creation of shapes. This factory will be an `interface` and will be implemented by a concrete `class`.

The `interface` should be named  `ShapeFactory` and the implementation can be named `ShapeFactoryImp` or `CShapeFactory`. This is preferrable to encoding the interface.

### Avoid Mental Mapping
Readers shouldn't have to mentally translate your names into other names they already know. This issue usually arises when not using problem domain or solution domain terms. 

This is  a problem with single-letter variable names. However, a counter can have variables name `i`, `j` and k as this is traditional. 

### Class Names
Classes and Objects should have noun or noun like phrase names. For example, `Customer`and `AddressParser`.

### Method Names
Methods should have verbs or verb like phrase names. For example, `deletePage` and  `postPage`. 

Accessors, mutators and predicates should be named for their value and prefixed with `get`, `set` and `is` according to the javabean standard.

``` java
String name = employee.getName();
customer.setName("Mike")
if (paycheck.isPosted()) ...
```

When constructors are overloaded, use static factory methods with names that describe the arguments. For example,

``` java
Complex fulcrumPoint = Complex.FromRealNumber(23.0);
```

is generally better than

``` java
Complex fulcrumPoint = new Complex(23.0)
```

Enforce their usage by making their corresponding constructor private.

### Don't Be Cute
Don't use slang or colloquialisms for naming variables.

### Pick One Word Per Concept
Pick one word for one abstract concept. For example, it is confusing to use `fetch`, `retrieve` and `get` as equivalent methods of different classes. 

Likewise, it's confusing to have a `Controller`, `DeviceManager` and `ProtocolController`.  The names lead you to expect different concepts but are the same.  Keep to a consistent lexicon.

### Don't Pun
Avoid using the same word for two purposes. Using the same term for two different ideas is essentially a pun. 

If you follow one word per concept rule, you will end up having many classes that have an `add` method.  As long as all `add` methods are semantically equivalent, all is well.

Do not use the word `add` when the method is not adding in the same sense. 

For example,  many classes use the `add` method will create a new value by adding or concatenating two existing values. Do not make a new `add` method which add as a parameter into a collection. This is semantically different. A word like `insert` or `append` is better. 