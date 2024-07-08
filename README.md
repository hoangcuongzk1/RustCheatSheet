
- [[#Variable Declaration and Data Types|Variable Declaration and Data Types]]
- [[#References and Pointers|References and Pointers]]
- [[#Functions and Code Blocks|Functions and Code Blocks]]
- [[#Structs and Data Types|Structs and Data Types]]
- [[#Conditionals and Loops|Conditionals and Loops]]
- [[#Strings and Arrays|Strings and Arrays]]
- [[#Scope and Modules|Scope and Modules]]
- [[#Operators and Macros|Operators and Macros]]
 
## Variable Declaration and Data Types
---

| Symbol   | Meaning              | Usage Scenarios                                            | Specific Examples                             |
| -------- | -------------------- | ---------------------------------------------------------- | --------------------------------------------- |
| `let`    | Declares a variable  | Declaring an immutable variable                            | `let x = 5;`                                  |
| `mut`    | Mutable variable     | Declaring a variable that can be changed                   | `let mut x = 5; x = 6;`                       |
| `:`      | Type annotation      | Annotating the type of a variable                          | `let x: i32 = 5;`                             |
| `type`   | Type definition      | Defining a new name for an existing type                   | `type Point = (i32, i32);`                    |
| `const`  | Constant declaration | Declaring an immutable value                               | `const MAX_POINTS: u32 = 100_000;`            |
| `static` | Static variable      | Declaring a static value, shared across the entire program | `static HELLO_WORLD: &str = "Hello, world!";` |

## References and Pointers
---

| Symbol | Meaning                                | Usage Scenarios                                  | Specific Examples                 |
| ------ | -------------------------------------- | ------------------------------------------------ | --------------------------------- |
| `&`    | Immutable reference                    | Borrowing data immutably                         | `let y = &x;`                     |
| `&mut` | Mutable reference                      | Borrowing data mutably                           | `let y = &mut x; *y = 6;`         |
| `*`    | Dereference operator or multiplication | Accessing value from a pointer or multiplication | `let y = *x;` or `let z = x * y;` |

## Functions and Code Blocks
---

| Symbol       | Meaning                                          | Usage Scenarios                                      | Specific Examples                                      |
|--------------|--------------------------------------------------|-----------------------------------------------------|-------------------------------------------------------|
| `fn`         | Function definition                              | Defining a new function                              | `fn add(a: i32, b: i32) -> i32 { a + b }`             |
| `->`         | Return type                                      | Specifying the return type of a function             | `fn add(a: i32, b: i32) -> i32 { a + b }`             |
| `{}`         | Code block                                       | Enclosing a code block or scope                      | `if x > 5 { println!("x is greater than 5"); }`       |
| `impl`       | Implementation block                             | Defining methods for a struct or enum                | `impl Point { fn new(x: i32, y: i32) -> Self { Self { x, y } } }` |

## Structs and Data Types
---

| Symbol   | Meaning              | Usage Scenarios                           | Specific Examples                                                 |
| -------- | -------------------- | ----------------------------------------- | ----------------------------------------------------------------- |
| `struct` | Struct definition    | Defining a complex data type              | `struct Point { x: i32, y: i32 }`                                 |
| `enum`   | Enum definition      | Defining a data type with multiple states | `enum Color { Red, Green, Blue }`                                 |
| `trait`  | Trait definition     | Defining shared behavior for types        | `trait Printable { fn print(&self); }`                            |
| `impl`   | Implementation block | Defining methods for a struct or enum     | `impl Point { fn new(x: i32, y: i32) -> Self { Self { x, y } } }` |

## Conditionals and Loops
---

| Symbol  | Meaning               | Usage Scenarios                                    | Specific Examples                                                                             |
| ------- | --------------------- | -------------------------------------------------- | --------------------------------------------------------------------------------------------- |
| `if`    | Conditional statement | Checking a condition and executing code            | `if x > 5 { println!("x is greater than 5"); }`                                               |
| `else`  | Alternative branch    | Executing when the if condition is not met         | `if x > 5 { println!("x is greater than 5"); } else { println!("x is not greater than 5"); }` |
| `for`   | For loop              | Looping over a collection                          | `for i in 0..5 { println!("{}", i); }`                                                        |
| `while` | While loop            | Looping while a condition is met                   | `while x < 5 { x += 1; }`                                                                     |
| `loop`  | Infinite loop         | Infinite loop until a break statement              | `loop { println!("looping"); break; }`                                                        |
| `match` | Pattern matching      | Matching patterns and executing corresponding code | `match x { 1 => println!("One"), _ => println!("Not One"), }`                                 |

## Strings and Arrays
---

| Symbol   | Meaning                     | Usage Scenarios                           | Specific Examples                              |
| -------- | --------------------------- | ----------------------------------------- | ---------------------------------------------- |
| `&str`   | String slice                | Declaring an immutable string             | `let s: &str = "hello";`                       |
| `String` | Dynamic string              | Declaring a dynamically allocated string  | `let s = String::from("hello");`               |
| `[]`     | Array                       | Declaring and accessing array elements    | `let arr = [1, 2, 3]; println!("{}", arr[0]);` |
| `()`     | Tuple or function call      | Declaring a tuple or calling a function   | `let t = (1, "hello"); println!("{}", t.0);`   |
| `vec!`   | Macro for creating a vector | Creating a vector with specified elements | `let v = vec![1, 2, 3];`                       |


## Scope and Modules
---

| Symbol | Meaning                   | Usage Scenarios                              | Specific Examples                                                              |
| ------ | ------------------------- | -------------------------------------------- | ------------------------------------------------------------------------------ |
| `::`   | Path separator or module  | Accessing functions or types within a module | `std::io::stdin()`                                                             |
| `mod`  | Module definition         | Defining a module                            | `mod my_module { pub fn my_function() { println!("Hello from my_module"); } }` |
| `use`  | Bringing items into scope | Importing functions, structs, or modules     | `use std::collections::HashMap;`                                               |
| `pub`  | Public visibility         | Making functions or structs public           | `pub fn my_function() { println!("Hello"); }`                                  |

## Operators and Macros
---

| Symbol       | Meaning                                          | Usage Scenarios                                      | Specific Examples                                      |
|--------------|--------------------------------------------------|-----------------------------------------------------|-------------------------------------------------------|
| `=>`         | Match arm expression                             | Specifying the expression for each match arm         | `match x { 1 => println!("One"), _ => println!("Not One"), }` |
| `!`          | Macro or logical negation                        | Calling a macro or negating a boolean expression     | `println!("Hello, world!");` or `if !x {}`             |
| `?`          | Question mark operator                           | Quick error handling in function returns             | `let file = File::open("path")?;`                      |
| `as`         | Type casting                                     | Casting a value to another type                      | `let x = 5 as f64;`                                    |
| `_`          | Placeholder or discard value                     | Ignoring a value in pattern matching or unused variable | `let _ = x;` or `match x { _ => () }`                  |
| `;`          | Statement terminator                             | Ending a statement                                   | `let x = 5;`                                          |

