The Builder pattern was introduced to solve some of the problems with Factory and Abstract Factory design patterns when an Object contains lots of attributes.

You don't have to immediately pass in all parameters, we can define them as we go along.


We can chain the methods as each method returns reference to the builder;