## Lists
List is a sub-interface of the Java collections interface.  Found in java.util.* package.
- Contains index-based methods to insert, update, delete, and search.
- Contains duplicate elements
- can store null elements
- preserves insertion order
- allows positional insertion and access of elements
- implementations are ArrayList, LinkedList

## Set
Set is also extends collection interface in java. Also found in java.util.* package.
- does not allow duplicate elements
- o not maintain insertion order
- does not have a get method for index
- can traverse with iterator

``` java

Set<String> Set 

```

## Map
Java map is found in the java.util.Map package. Has a mapping between a key and a value.
- map can store pairs of keys and values
- each key is linked to a specific value
- you can look up values using the key.
- does not allow duplicate elements
- single null key

``` java
Map<Integer, String> map = new HashMap<Integer, String>();

//adding to a map
map.put(100, "Amit");

//traversing elements in a map

for ( Map.Entry m : map.entrySet()) {
	System.out.println(m.getKey() + " " + m.getValue());
}

```


