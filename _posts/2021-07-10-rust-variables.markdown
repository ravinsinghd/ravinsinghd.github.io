---
layout: post
title: 'Rust programming #3 | Rust variables'
description: 'We will learn about how to declare and use Rust variables'
tags: ['Rust', 'Let', 'Const']
comments: true
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

The above code will be compiled without any issue. Since we mark the variable as mutable, we can update the value of the variable.

### Const

Another variable type is **const**. Const is like let, but this value cannot be changed. This does not support **mut** keyword.Also const can be declared in any scope. For example you can declare const variable in the global scope. let see a example below,

```rs
const B: i32 = 10;
fn main() {
    println!("Hello, world!{}", B);
}
```

See, how the variable **B** is declared outside the main function. This is valid declaration it will work, but if you try to declare **let** variable outside the main function, you will get error. The **const** variable are available for entire program runtime within the scope they declared.So you can use this variables for keep some values which will not change in the program.

**Const** variables should have data type annotation. On the above example const variable **B** is annotated with **i32**, that means const B is a 32 bit integer.We can learn about different type of data types in next post. For now just remember **const** variable should have type annotation.

**Const** variable value should constant expression. That means the value of the const variable should be available in the compile time itself, you can't call function and assign the return value as const variable value.

And as per the Rust naming convention it's recommended to name the **const** variable all upper case.You can use underscore between words. For example below are some of the **const** variable names.

```rs
const MAX_VALUE: i32 = 100;
const MIN_VALUE: i32 = 10;
const VALUE: i32 = 30;
```

### Shadowing

In Rust we can override mutable variable value by shadowing the variable. For example, you got the some value from API, it's string type but you want that variable in the integer data type. For this use case we normally declare another one variable with the different name and assign the converted value to the variable. But in Rust we can do the following,

```rs
fn main() {
    let a = "10";
    let a = a.parse::<i32>().unwrap();
    println!("{}", a);
}
```

In the above program we are parse the string value to integer and assign the value to the same variable. But the difference is since we are updating the mutable variable value also we use the **let** keyword again. When you use the **let** keyword again in the variable which already exist Rust effectively create new variable in the memory with the same name and remove the existing one from memory. Since we are creating entirely new variable we can change the data type as well. That is why we are able to assign the integer value to the variable which declared as string type first.It will be useful feature for reuse the variable without declaring new variable.

Next post will dive deeper into Rust data types.Also this rust series available as video in my [YouTube channel](https://www.youtube.com/channel/UC4w12aiYyyYGqFzIkBlHlBQ).
