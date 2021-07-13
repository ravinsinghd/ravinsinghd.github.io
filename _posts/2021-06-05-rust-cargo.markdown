---
layout: post
title: 'Rust programming #2 | Cargo and Rust variables'
description: 'We will learn about how to run and build Rust programs using cargo tool and how to declare basic variables in Rust program'
tags: ['Rust', 'Cargo']
---

### Cargo

In this series we are learning Rust. if you want to follow from the start please go to this link, where we have all the post in the Rust series. on this post we are going to learn about tool called cargo.

Cargo is a command line tool which will help you to scaffolding,building,test and manage packages for the Rust programmes. If you are used npm for nodejs, then cargo is similar to the Rust ecosystem. If you followed the previous post and installed Rust then you system already has cargo installed. To verify you can run below command and see if it's log the cargo version

```sh
cargo --version
```

> if you see any errors, commend that errors I will help you out.

#### Scaffolding project

let's create one project with cargo and will go through the default directory structure. Go to any empty folder and run below command

```sh
cargo new hello_cargo
```

It should create one binary application called hello_cargo. Open the folder in any editor, you will see the project with default folders and files like below

![cargo default folders]({{ site.baseurl }}/assets/images/posts/cargo_and_rust_variable/cargo_default_folder.png)

> Ignore the target folder and cargo.lock file. I am using Rust extension in my editor, It will auto build any Rust project open in the editor.

Let's go through the files one by one

#### Cargo.toml

Every application created with cargo will have Cargo.toml file. It used for manage application metadata,configuration and dependencies. Open Cargo.toml file you will see configuration like below.

```toml
[package]
name = "hello_cargo"
version = "0.1.0"
edition = "2018"

# See more keys and their definitions at https://doc.rust-lang.org/cargo/reference/manifest.html

[dependencies]
```

The name property use to define name of the application. Here it's take from the cargo new command argument.

The version property defines the version for this application. if you are creating library which published in crates, then this version number will be used to manage release cycle and dependency management. Will learn how to create and publish crates in upcoming posts. For now keep the default value.

The edition property defines which edition of the Rust compiler you are going to use for compile the application. Will learn about editions in later posts for now keep the default value.

The dependencies section used for listing your dependencies for this application. As of now we do not have any dependencies for our application, So it is empty. When we are start expanding our application we can pull dependencies from crates and use in our application.

#### src/main.rs

Cargo created main file inside the src folder. Currently main file has default function which will print "hello world" when you run it. when working with cargo you should add all your source file inside the src folder.

#### Build

Now open command prompt and navigate to the application folder. Then run the below command

```sh
cargo build
```

Now cargo, build your application and create executable in the folder called target.You can run that application by running the executable file as shown in the below image

![cargo build]({{ site.baseurl }}/assets/images/posts/cargo_and_rust_variable/cargo_build.png)

In the command output this build mentioned as unoptimized. This is because cargo build by default will create the build with debug info and without much optimization. This build type should be used only for development and debug. This build type will be compile fast and run slow. For production you should compile application using below command

```sh
cargo build --release
```

This build type will take additional time to compile the code but it will run fast.

#### Run

while you develop you may want to see the output quickly. For that you can use the run command as below.

```sh
cargo run
```

This command will compile your application and run the executable automatically.

![cargo run]({{ site.baseurl }}/assets/images/posts/cargo_and_rust_variable/cargo_run.png)

Incase you want to check if the application compile successfully but don't want to run the application, you can use the below command

```sh
cargo check
```

This command will compile and report if any error in the application. But will not create executable or run application. This will save time when working on bigger application.

![cargo check]({{ site.baseurl }}/assets/images/posts/cargo_and_rust_variable/cargo_check.png)

### Rust variables

Now let's declare variable in our application and run it using cargo. open main.rs and type below code

```rs
fn main() {
    let x = 10;
    println!("The value of x {}", x);
}
```

**let** is the keyword we can use to declare the variable in Rust. Here we created variable called x and assign 10 as a value.

In the next line we called print line macro. On this macro you can use the curly braces to print variables. So in run time rust will take the x value and print instead of the curly braces. Note i mentioned println! as macro not a function or keyword. Because while compile Rust compiler will update the println!. Will learn about macros in details in upcoming post.

Now run this application using cargo run.

![cargo variable]({{ site.baseurl }}/assets/images/posts/cargo_and_rust_variable/cargo_variable.png)

In Rust all variables by default created as immutable. In the next post will see what is immutable variable and how to use mutable & const variables.
