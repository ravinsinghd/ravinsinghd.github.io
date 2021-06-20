---
layout: post
title: 'Rust programming #2 | Cargo and Rust variables'
---

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

![cargo default folders]({{ site.baseurl }}/assets/images/posts/cargo_and_rust_variable/cargo_default_folders.png)

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
