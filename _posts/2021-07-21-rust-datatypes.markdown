---
layout: post
title: 'Rust programming #4 | Data types (WIP)'
description: 'We will learn about list of data type available in Rust and when to use what data types'
tags: ['Rust', 'Data Types']
comments: true
---

Rust is statically typed language. That means, all the variables should have data type associate with them in the compile time. In some case Rust will infer the data types from variable value.But if more than one datatype possible for value, then the compiler will force developer to explicitly assign the data type for the variable.

Below are the list of data types available in Rust

- Integer
- Boolean
- Char
- Floating-point number
- Tuple
- Array

### Integer

Integer data type used for storing signed and unsigned integer value. Signed means the number has Negative or positive sign associated with them.For example -10, -2, +20 are signed integer.Normally we will use sign, only for negative number. if the integer does not has any sign then that is consider as positive integer.For signed and unsigned integer we have separate data types.

#### Signed Integer

Singed integers can store positive and negative integers.Below code example has different signed integer data types

```rs
fn main() {
    let a: i8 = 10;
    let b: i16 = -20;
    let c: i32 = 10;
    let d: i64 = 20;
    let e: i128 = 30;
    let f: isize = -40;
}
```

All the signed integer data types are combination of **i** and the space it can take. For **i8** integer will take up to 8 bit space, **i16** it takes upto 16 bit space and so on. The last data type, **isize** means it take space based on the system architecture. For example if you have 32 bit machine, it will take upto 32 bit space. If you have 64 bit machine it will take upto 64 bit space.

if you did not mention any data type for integer Rust will assign default data type **i32**. For example, in the below code block the data type for the variable **a** will be infer as **i32**.

```rs
fn main() {
    let a = 10;
}
```

#### Unsigned integer

Unsigned integers can store only positive integers.Below code example has different unsigned integer data type

```rs
fn main() {
    let a: u8 = 10;
    let b: u16 = 20;
    let c: u32 = 10;
    let d: u64 = 20;
    let e: u128 = 30;
    let f: usize = 40;
}
```

All unsigned integers data types are combination of **u** and the bit space it can take. Unsigned integers have bit space same as singed integer, from 8 to 128 bit and size which will take bit space based on system architecture.

### Boolean

Boolean data type can store value either True or False. This data type mostly used as flag. For example we can use boolean as below

```rs
fn main() {
    let a = true;
    let b: bool = false;
}
```

### Char

Char data type used for storing single letter. You can't store more than one letter in char data type. For that we have to use string data type. We will learn about string data type in separate post. In char data type you can store all valid unicode character.

```rs
fn main() {
    let a = 'a';
    let b: char = '😊';
}
```

### Floating-point number

Floating point number used for store number with decimal points.For example 1.3 or 3.14. Below is the example code

```rs
fn main() {
    let a = 1.3;
    let b: f64 = 3.14;
    let c: f32 = -3.14;
}
```

### Tuple

All the above data types we learned are called **scalar data types**. Tuple and Array data types are called **compound data types**.The difference between scalar and Compound data types is scalar data types can hold single value, but compound data types can have more than one value per variable. Will see Tuple first.

```rs
fn main() {
    let a = (10, "Test", 1.3);
    let b: (u32, f64) = (10, 3.14);
}
```

A tuple can hold multiple values with different data types. We can access the individual values from tuple by destructuring or using dot (.) as shown blow.

```rs
fn main() {
    let a = (10, "Test", 1.3);
    let b: (u32, f64) = (10, 3.14);
    let (c, d, e) = a;
    println!("{}", a.0);
}
```

**_let (c, d, e) = a_** in this code we are breaking the tuple to individual value and assign to the variables. After this we can use this variable c,d,e like any other variable. **_println!("{}", a.0);_** In this code we are accessing the tuple value by it's index. **_a.0_** will return the first value from the tuple.

### Array

Array same like tuple, it can hold multiple values. But array requires all the value are in same data type. Like tuple we can't put different type of data types in array.

```rs
fn main() {
    let a = [1, 2, 3, 4, 5];
    let b = [3; 5];
    let c = ['a', 'b', 'c'];
}
```

On the above example **a** is an array containing five i32 values. As we learn before this variable data types should be same. In the next line we are creating new array with five values all are 3. This line is same as writing **_let b = [3, 3, 3, 3, 3];_**. On third line we have array with all value are in char data type.

We can access the array value using the index of the value.

```rs
fn main() {
    let a = [1, 2, 3, 4, 5];
    let b = [3; 5];
    let c = ['a', 'b', 'c'];
    println!("{}", a[0]);
    println!("{}", b[2]);
}
```

The above two compound data types are fixed length. That means, once we declare this variable we can't grow or shrink the variable size. For that type of use case we have another data type called **vector**. We will learn about the vector data type in separate post.

**if you have any doubt or suggestion please comment. I will address them.**
