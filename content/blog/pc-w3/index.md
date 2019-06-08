---
title: Pre-Course Week 3 - What the Hash?
date: "2019-03-31T23:46:37.121Z"
---

Weeks 2 and 3 of the Makers pre-course material delve deeper into the fundamentals of [object orientated languages](https://en.wikipedia.org/wiki/Object-oriented_programming) (Makers starts with [Ruby](https://www.ruby-lang.org/en/) for its easy syntax). Over the two week period, students follow a curriculum covering topics such as arrays, hashes and methods, with challenges set to test one’s understanding of each new topic as they are introduced.

As well as encouraging the mastery of Ruby’s syntax, the challenges help build confidence in writing real-world, procedural programmes.

*I found the chapter on hashes confusing because I had heard the word “hash” used in a myriad of contexts.*

Is there a difference between a hash used to store data the way that a dictionary does and a hash used in the context of cryptography?

My research uncovered the following..

### What’s a hash?
*A [hash function](https://en.wikipedia.org/wiki/Hash_function) is any function that can be used to map data of arbitrary size onto data of a fixed size. The values returned by a hash function are called hash values, hash codes or hashes.*


Hashing data is a common practice in computer science and is used for several different purposes. Examples include cryptography, compression, checksum generation, and data indexing.

### Hash Table
A typical use-case for hash functions is hash tables, which are data structures that associate lookup-values (keys) with other values.

In a [hash table](https://www.hackerearth.com/practice/data-structures/hash-tables/basics-of-hash-tables/tutorial/) (as opposed to an array), large key values are hashed into an integer by passing them through a hash function. This element can be used as an index to store the original element, which falls into the hash table. The element is stored in the hash table where it can be quickly retrieved using the hashed key.

### Checksums
Checksums are a way of checking the integrity of a file by comparing its hash value (usually represented as a string) with the hash of the original file. Depending on the file size, the hash value will likely be no more than a few dozen [ASCII characters](http://www.asciitable.com/). If the hash values of the two files match, there is a high probability that the data has not been accidentally altered or corrupted.

### Cryptography
In cryptography, the aim is to make it computationally difficult to figure out the input that led to a given hash value. An obvious application for cryptography is password protection. Instead of storing users’ passwords on a server (that can then be compared to a user’s input to confirm/deny whether the entered password is correct), cryptographic hashes of the password can be stored on the server. So, if someone looks at the server for passwords, it will be challenging for them to reverse engineer the hash value back into the password.

---

Regarding terminology, using *hash tables* as an example, the takeaway here is that it is called a *hash table* because it relies on a *hash function* to produce hash values (hashes).