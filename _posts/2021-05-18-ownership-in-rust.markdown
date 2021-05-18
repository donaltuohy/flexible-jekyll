---
layout: post
title: Ownership in Rust
date: 2021-05-18 07:44:20 +0300
description: Learning about memory usage in Rust.
img: cpu1.jpg # Add image post (optional)
fig-caption: # Add figcaption (optional)
tags: [Rust, Ownership, Memory]
---
I've started learning Rust recently. The first topic that has differed from other Languages I am familiar with is how Rust deals with memory usage. Rust is able to guarantee memory safety without needing a garbage collector. This is possible with a feature called *Ownership*. 


### Scope of a variable
When we talk about the scope of a variable, it is the range within the program for which a variable is valid. Imagine we have a variable like this :

```rust
let s = "hello";
```

This variable is valid until it's scope ends.

```rust
// s is not valid until as it hasn't been defined yet.

{ 
    let s = "hello"; // s is valid from here

    println!("{}", s); // s can be used as it's still in scope
} 

// s is now unusable as the scope it was defined in is over.

```

### Memory and Allocation
When we're looking to allocate memory for *mutable variables*, we have the problem that the amount of memory needed is unknown at compile time. We need to do two things:

1. We must request the memory from the operating system at runtime.
2. Once we are finished with the variable, we must return the memory to the operating system. Otherwise we would start wasting memory.

The first step is pretty automatic and seemless in most programming languages. For the second part however, there's multiple ways this is dealt with. 
In languages with a Garbage Collector, it is looked after and you don't need to think about it. When a language doesn't have a Garbage Collector,
it is up to the programmer to return the memory explicitly. 

This is where scopes come into play in Rust. Memory is automatically returned once the variable that was using it goes out of scope. If we look at the the code snipped above, when the block is closed with a curly bracket, the variable `s` goes out of scope. When a scope ends in Rust, a special function, `drop`, is called. This function returns the memory of any variables that were in the scope.


![Ownership]({{site.baseurl}}/assets/img/sunset.jpg)

