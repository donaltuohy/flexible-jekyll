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



## Three rules of Ownership
1. Each value in Rust has a owner variable.
2. Only one owner is allowed at any time.
3. The value will be dropped when the owner goes out of scope.

![Ownership]({{site.baseurl}}/assets/img/sunset.jpg)

