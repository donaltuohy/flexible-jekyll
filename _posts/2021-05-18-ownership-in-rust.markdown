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


![Ownership]({{site.baseurl}}/assets/img/sunset.jpg)

