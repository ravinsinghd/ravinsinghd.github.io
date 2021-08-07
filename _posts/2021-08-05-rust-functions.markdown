---
layout: post
title: 'Rust programming #5 | Functions'
description: 'We will learn about how to declare and use functions in Rust.'
tags: ['Rust', 'functions']
slug: rust-function
comments: true
---

In this Rust series today we are going to learn about how to use the functions. Functions are the basic building block of Rust. if you ever created and run a Rust program you already wrote functions. Let's see an example

```rs
fn main() {
    println!("Hello world!");
}
```

Here we have a function called `main`. The function will be declared using the `fn` keyword. This is a special function, you need to have in your program. This will act as an entry point for the program execution. let see an example that will have more than one function.

```rs
fn main() {
    println!("Hello world!");
}

fn get_new_world() -> &'static str {
    "World"
}
```

Above example, we have a function called `get_new_world`. As you can see we are using snake case for function names. Rust naming convention recommends using snake case for function names. After function name, we have an arrow (->), which is used to declare the return type of the function. For this function, the return type is a string literal with a static lifetime. we will learn more about `string` and `lifetimes` in the upcoming post. For now, just consider, this function will return some string when it's called.

Next line we have the string `World`. But we did not return or do any operation on the string. if you compile and run this code, It will execute without any problem. That is because when we have expression as the last line in function that will be considered as function return value.

if you are confused about what is expression, don't worry 😀. let see that in detail. Rust functions consist of statements and expressions. Statements are instructions the perform some operation but it will not return any value. But expressions will return value. So `let a = 10;` is the statement. Because all this instruction does is, create a variable `a` and assigning value 10 to the variable. It does not return any value. let see instruction `7 + 3`. This instruction performs an addition operation and returns a value as '10'. These instructions are called expressions.

Hope now you are clear about the statement and expression.Now, come back to our `get_new_world` function. The instruction `World` is an expression because it creates a string literal called `world` and returns it. So whenever you have expression as a lost line in your program without semicolon(;), Rust will consider that value as function return value.

#### Function call

Now we have a function called `get_new_world` and it returns string literal. Let's call this function, in our main function.

```rs
fn main() {
    let world = get_new_world();
    println!("Hello {}!", world);
}

fn get_new_world() -> &'static str {
    "World"
}
```

To call a function we should use the function name and set of parentheses at end of the function name. we are calling function `get_new_world` and assign the return value to variable `world`.Since the function returns a value we can assign the return value to some variable. incase the function does not return any value then we can't assign. The compiler will throw an error in that case.

Also, our `get_new_world` function is defined after main function. Some languages will not allow calling a function that is defined after the calling function. But Rust does not care where you defined the function as long as you have a valid function in that file you can call that.

#### Function argument

A function can accept parameters. When defining a function we can define some parameters in the function signature. This parameter should have a data type associate with them, so Rust can validate the parameter when functions get called in a different part of the code. let see an example

```rs
fn main() {
    let result = multiply_by_5(10);
    println!("Value is {}", result);
}

fn multiply_by_5(value: i32) -> i32 {
    value * 5
}
```

Here we have a function called `multiply_by_5` which will multiply any value it received as a parameter with 5 and return the resulting value. While defining this parameter we have also mentioned the data type it will accept. So when any other parts of the code call this function it should pass the `i32` datatype value as a parameter otherwise the compiler will throw an error.

Great!!!. Now we have most of the basic topics covert in Rust. The next post will learn about how to control the flow of our program execution. Please comment with your feedback and suggestions, it will be helpful to improve this series.
