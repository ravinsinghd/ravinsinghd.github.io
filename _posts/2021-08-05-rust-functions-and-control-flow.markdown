---
layout: post
title: 'Rust programming #5 | Functions and control flow'
description: 'We will learn about how to declare and use functions in Rust. Also will learn about how to use the control flow such as while,loop,for and if in Rust '
tags: ['Rust', 'functions', 'for', 'if', 'while']
comments: false
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

To call a function we should use function name and set of parentheses at end of the function name. So we are calling function _get_new_world_ and assign the return value to variable `world`.Since the function returning value we can assign the return value to some variable. incase the function does not return any value then we can't assign. Compiler will trow error in that case.

Also, our _get_new_world_ function is defined
