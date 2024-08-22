Hash functions play a crucial role in various applications such as data storage, retrieval, and cryptography.

In data structures and algorithms (DSA), hash functions are primarily used in hash tables, which are essential for efficient data management.

# What is a Hash Function?

A **has function** is a function that takes an input (or 'message') and returns a fixed-size string of bytes.

The output, typically a number, is called hash code or hash value. 

The main purpose of a hash function is to efficiently map data of arbitrary size to fixed-size values, which are often used as indexes in has tables.

## Key Properties of Hash Functions

- **Deterministic:** consistently produces the same output for the same input
- **Fixed Output Size**: output of a hash function should have a fixed size, regardless of the size input.
- **Efficiency**: should be able to process input quickly
- **Uniformity**: should distribute the hash values uniformly across the output space to avoid clustering.
- **Pre-image Resistance**: it should be computationally infeasible to reverse the hash function, i.e., to find the original input given a hash value.
- **Collision Resistance**: It should be difficult to find two different inputs that produce the same hash value.
- **Avalanche Effect**: A small change in the input should produce a significantly different hash value.

# Applications of Hash Functions
- **Hash Tables**: The most common use of hash functions in DSA is in hash tables, which provide an efficient way to store and retrieve data.
- **Data Integrity**: Hash functions are used to ensure the integrity of data by generating checksums.
- **Cryptography**: In cryptographic applications, hash functions are used to create secure hash algorithms like SHA-256.
- **Data Structures**: Hash Functions are utilised in various data structures such as Bloom filters and hash sets.

# Types

There are many has functions that use numeric or alphanumeric keys. This article focuses on discussing different hash functions:
1. Division Method
2. Multiplication Method
3. Mid-Square Method
4. Folding Method
5. Cryptographic Hash Functions
6. Universal Hashing
7. Perfect Hashing

## 1. Division Method
Dividing the key by a prime number and using the remainder as the hash value.

``` java
h(k)= k mod m

where k is the key and m is a prime number
```

Pros:
- simple to implement
- works well when m is a prime number
Cons:
- poor distribution if m is not chosen wisely

## 2. Multiplication Method
A constant AA(0 < A < 1) i used to multiply the key. The fractional part of the product is then multiplied by m to get the has value.

``` java
h(k) = []
```