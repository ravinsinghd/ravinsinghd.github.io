---
layout: post
title: 'Rust programming #5 | Functions'
description: 'We will learn about how to declare and use functions in Rust.'
tags: ['Rust', 'functions']
slug: rust-function
comments: true
---

On this Rust series today we are going to learn about how to use the functions and control flow. such as, loop, while, for and if.Functions are basic building block of Rust. if you ever created and run a Rust program you already wrote functions. Lets see an example

```rs
fn main() {
    println!("Hello world!");
}
```

Here we have function called _main_. The function will be declared using _fn_ keyword. This is a special function, you need have in your program. This will act as entry point for the program execution. let see an example which will have more than one functions.

```rs
fn main() {
    println!("Hello world!");
}

fn get_new_world() -> &'static str {
    "World"
}
```

Above example we have a function called _get_new_world_. As you can we are using snake case for function names. Rust naming convention recommend to use snake case for function names. After function we have arrow (->), which is used for declare the return time of the function. For this function the return type is string literal with static life time. we will learn about _string_ and _lifetimes_ in upcoming post.for now just consider this function will return some string when it's called.

Next line we have string _World_. But we did not return the string. if you compile and run this code,it will execute without any problem. That because when we have expression as last line in function that return value will be automatically return when the function called.

if you are confused about what is expression, don't worry 😀, let see that in detail. Rust functions consist of statements and expressions.statements are instruction the perform some operation but it will not return any value. But expressions will return value. So `let a = 10;` is the statement. Because all this instruction do is, create a variable 'a' and assigning value 10 to the variable.It does not return any value. let see instruction `7 + 3`. This instruction perform addition operation and return value as '10'. This instructions called as expression.

So,hope you are clear about statement and expression.Now, comeback to our _get_new_world_ function, the instruction `World` is a expression because it's create string literal called _world_ and return it. So when ever you have expression as a lost line in your program without semicolon(;), Rust will consider that value as function return value.

#### Function call

Now we have function called _get_new_world_ and it returns string literal. Lets call this function in our main function.

```rs
fn main() {
    let world = get_new_world();
    println!("Hello {}!", world);
}

fn get_new_world() -> &'static str {
    "World"
}
```

To call a function we should use function name and set of parentheses at end of the function name. we are calling function `get_new_world` and assign the return value to variable `world`.Since the function returning value we can assign the return value to some variable. incase the function does not return any value then we can't assign. Compiler will trow error in that case.

Also, our `get_new_world` function is defined after main function. Some languages will not allow calling functions which defined after the calling function.But Rust does not care where you defined the function as long as you have valid function in that file you can call that.

#### Function argument

Function can accept parameter. When define function you can define some parameter in function signature.This parameter should have data type associate with them, so Rust can validate the parameter when function get called in different part of the code.let see an example

```rs
fn main() {
    let result = multiply_by_5(10);
    println!("Value is {}", result);
}

fn multiply_by_5(value: i32) -> i32 {
    value * 5
}
```

Here we have function called `multiply_by_5` which will multiply any value it received as parameter with 5 and return the resulting value. While define this parameter we have also mentioned data type it will accept. So when any other parts of the code call this function it should pass `i32` datatype value as parameter otherwise compiler will throw error.

Great!!!. Now we have most of the basic topic covert.Next post will learn about how to control the flow of our program execution. Please comment your feedback and suggestions, it will be helpful to improve this series.
