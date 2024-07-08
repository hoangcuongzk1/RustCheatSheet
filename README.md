
- [Symbols](#symbols)
  - [Variable Declaration and Data Types](#variable-declaration-and-data-types)
  - [References and Pointers](#references-and-pointers)
  - [Functions and Code Blocks](#functions-and-code-blocks)
  - [Structs and Data Types](#structs-and-data-types)
  - [Conditionals and Loops](#conditionals-and-loops)
  - [Strings and Arrays](#strings-and-arrays)
  - [Scope and Modules](#scope-and-modules)
  - [Operators and Macros](#operators-and-macros)
  - [Formatting and Printing](#formatting-and-printing)


- [[#Symbols|Symbols]]
	- [[#Symbols#Variable Declaration and Data Types|Variable Declaration and Data Types]]
	- [[#Symbols#Ownership and Lifetimes|Ownership and Lifetimes]]
	- [[#Symbols#References and Pointers|References and Pointers]]
	- [[#Symbols#Functions and Code Blocks|Functions and Code Blocks]]
	- [[#Symbols#Structs and Data Types|Structs and Data Types]]
	- [[#Symbols#Conditionals and Loops|Conditionals and Loops]]
	- [[#Symbols#Strings and Arrays|Strings and Arrays]]
	- [[#Symbols#Scope and Modules|Scope and Modules]]
	- [[#Symbols#Operators and Macros|Operators and Macros]]
	- [[#Symbols#Formatting and Printing|Formatting and Printing]]


## Symbols
---
### Variable Declaration and Data Types

| Symbol  | Meaning                       | Usage Scenarios                                             | Specific Examples                                  |
| ------- | ----------------------------- | ----------------------------------------------------------- | -------------------------------------------------- |
| `let`   | Declares a variable           | Declaring an immutable variable                             | `let x = 5;`                                       |
| `mut`   | Mutable variable              | Declaring a variable that can be changed                    | `let mut x = 5; x = 6;`                            |
| `:`     | Type annotation               | Annotating the type of a variable                           | `let x: i32 = 5;`                                  |
| `type`  | Type definition               | Defining a new name for an existing type                    | `type Point = (i32, i32);`                         |
| `const` | Constant declaration          | Declaring an immutable value                                | `const MAX_POINTS: u32 = 100_000;`                 |
| `static`| Static variable               | Declaring a static value, shared across the entire program  | `static HELLO_WORLD: &str = "Hello, world!";`      |

### Ownership and Lifetimes

| Symbol    | Meaning             | Usage Scenarios                                            | Specific Examples                                                                             |
| --------- | ------------------- | ---------------------------------------------------------- | --------------------------------------------------------------------------------------------- |
| `'a`      | Lifetime annotation | Specifying the lifetime of a reference                     | `fn longest<'a>(x: &'a str, y: &'a str) -> &'a str { if x.len() > y.len() { x } else { y } }` |
| `'static` | Static lifetime     | Data lives for the entire duration of the program          | `let s: &'static str = "Hello, world!";`                                                      |
| `move`    | Ownership transfer  | Transferring ownership of captured variables into closures |                                                                                               |
- `move` 
```rust

let c = vec![1, 2, 3];  

let f = move || {  
    println!("{:?}", c);  
};  

println!("{}", c[0]); // 🚫

f();
```

```rust
let c = vec![1, 2, 3];  

println!("{}", c[0]); // ✅

let f = move || {  
    println!("{:?}", c);  
};  

f();
```

### References and Pointers

| Symbol | Meaning                            | Usage Scenarios                                | Specific Examples                        |
| ------ | ---------------------------------- | --------------------------------------------- | ---------------------------------------- |
| `&`    | Immutable reference                | Borrowing data immutably                      | `let y = &x;`                             |
| `&mut` | Mutable reference                  | Borrowing data mutably                        | `let y = &mut x; *y = 6;`                 |
| `*`    | Dereference operator or multiplication | Accessing value from a pointer or multiplication | `let y = *x;` or `let z = x * y;`         |

### Functions and Code Blocks

| Symbol | Meaning              | Usage Scenarios                                 | Specific Examples                                                 |
| ------ | -------------------- | ----------------------------------------------- | ----------------------------------------------------------------- |
| `fn`   | Function definition  | Defining a new function                         | `fn add(a: i32, b: i32) -> i32 { a + b }`                         |
| `->`   | Return type          | Specifying the return type of a function        | `fn add(a: i32, b: i32) -> i32 { a + b }`                         |
| `{}`   | Code block           | Enclosing a code block or scope                 | `if x > 5 { println!("x is greater than 5"); }`                   |
| `impl` | Implementation block | Defining methods for a struct or enum           | `impl Point { fn new(x: i32, y: i32) -> Self { Self { x, y } } }` |
| \| \|  | Closure definition   | quick define function inside existed code block |                                                                   |
- `||`
```rust
let c = vec![1, 2, 3];

let f = || {
    println!("{:?}", c);
};

f();

```


### Structs and Data Types

| Symbol       | Meaning                                          | Usage Scenarios                                      | Specific Examples                                      |
|--------------|--------------------------------------------------|-----------------------------------------------------|-------------------------------------------------------|
| `struct`     | Struct definition                                | Defining a complex data type                         | `struct Point { x: i32, y: i32 }`                     |
| `enum`       | Enum definition                                  | Defining a data type with multiple states            | `enum Color { Red, Green, Blue }`                     |
| `trait`      | Trait definition                                 | Defining shared behavior for types                   | `trait Printable { fn print(&self); }`                |
| `impl`       | Implementation block                             | Defining methods for a struct or enum                | `impl Point { fn new(x: i32, y: i32) -> Self { Self { x, y } } }` |

### Conditionals and Loops

| Symbol       | Meaning                                          | Usage Scenarios                                      | Specific Examples                                      |
|--------------|--------------------------------------------------|-----------------------------------------------------|-------------------------------------------------------|
| `if`         | Conditional statement                            | Checking a condition and executing code              | `if x > 5 { println!("x is greater than 5"); }`       |
| `else`       | Alternative branch                               | Executing when the if condition is not met           | `if x > 5 { println!("x is greater than 5"); } else { println!("x is not greater than 5"); }` |
| `for`        | For loop                                         | Looping over a collection                            | `for i in 0..5 { println!("{}", i); }`                |
| `while`      | While loop                                       | Looping while a condition is met                     | `while x < 5 { x += 1; }`                             |
| `loop`       | Infinite loop                                    | Infinite loop until a break statement                | `loop { println!("looping"); break; }`                |
| `match`      | Pattern matching                                 | Matching patterns and executing corresponding code   | `match x { 1 => println!("One"), _ => println!("Not One"), }` |

### Strings and Arrays

| Symbol  | Meaning                            | Usage Scenarios                                                                  | Specific Examples                                   |
| ------- | ---------------------------------- | -------------------------------------------------------------------------------- | -------------------------------------------------- |
| `&str`  | String slice                       | Declaring an immutable string                                                    | `let s: &str = "hello";`                            |
| `String`| Dynamic string                     | Declaring a dynamically allocated string                                         | `let s = String::from("hello");`                    |
| `[]`    | Array                              | Declaring and accessing array elements                                           | `let arr = [1, 2, 3]; println!("{}", arr[0]);`      |
| `()`    | Tuple or function call             | Declaring a tuple or calling a function                                          | `let t = (1, "hello"); println!("{}", t.0);`        |
| `vec!`  | Macro for creating a vector        | Creating a vector with specified elements                                        | `let v = vec![1, 2, 3];`                            |

### Scope and Modules

| Symbol       | Meaning                                          | Usage Scenarios                                      | Specific Examples                                      |
|--------------|--------------------------------------------------|-----------------------------------------------------|-------------------------------------------------------|
| `::`         | Path separator or module                         | Accessing functions or types within a module         | `std::io::stdin()`                                     |
| `mod`        | Module definition                                | Defining a module                                    | `mod my_module { pub fn my_function() { println!("Hello from my_module"); } }` |
| `use`        | Bringing items into scope                        | Importing functions, structs, or modules             | `use std::collections::HashMap;`                       |
| `pub`        | Public visibility                                | Making functions or structs public                   | `pub fn my_function() { println!("Hello"); }`          |

### Operators and Macros

| Symbol       | Meaning                                          | Usage Scenarios                                      | Specific Examples                                      |
|--------------|--------------------------------------------------|-----------------------------------------------------|-------------------------------------------------------|
| `=>`         | Match arm expression                             | Specifying the expression for each match arm         | `match x { 1 => println!("One"), _ => println!("Not One"), }` |
| `!`          | Macro or logical negation                        | Calling a macro or negating a boolean expression     | `println!("Hello, world!");` or `if !x {}`             |
| `?`          | Question mark operator                           | Quick error handling in function returns             | `let file = File::open("path")?;`                      |
| `as`         | Type casting                                     | Casting a value to another type                      | `let x = 5 as f64;`                                    |
| `_`          | Placeholder or discard value                     | Ignoring a value in pattern matching or unused variable | `let _ = x;` or `match x { _ => () }`                  |
| `;`          | Statement terminator                             | Ending a statement                                   | `let x = 5;`                                          |
| `#`          | Attribute                                        | Applying metadata to modules, crates, or functions   | `#[derive(Debug)] struct Point { x: i32, y: i32 }`     |


### Formatting and Printing

| Symbol       | Meaning                                          | Usage Scenarios                                      | Specific Examples                                      |
|--------------|--------------------------------------------------|-----------------------------------------------------|-------------------------------------------------------|
| `:?`         | Debug formatting                                 | Printing or formatting output for debugging purposes | `println!("{:?}", my_variable);`                       |

