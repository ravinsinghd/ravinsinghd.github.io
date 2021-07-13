---
layout: post
title: 'Rust programming #3 | Rust variables'
---

In this post will learn about Rust variables. on Rust all the variables by default is immutable. Immutable means, if you assign any value to variable then you can't update value. In your code if your update the value of the immutable variable then compiler will throw error.

let see a example below

```rs
fn main() {
    let a = 10;
    println!("The value of a {}", a);
    a = 20;
}
```

if you are compile this code, then you will get error from compiler.

![Rust variable value re-assigned error]({{ site.baseurl }}/assets/images/posts/rust_variable/rust_reassign_error.png)

As we can see the compiler showing error about value assigned twice to the immutable variable. Because of this immutable property compiler can effectively manage the memory of the variables. Also it will be easy to maintain when the variable used in the concurrent programing.

Sometimes, you may want to make the variable mutable. For example when working with large data structures, updating the variable instead of creating new variable is more efficient.For such case you can use **_mut_** keyword as below.

```rs
fn main() {
    let mut a = 10;
    println!("The value of a {}", a);
    a = 20;
    println!("The value of a {}", a);
}
```
