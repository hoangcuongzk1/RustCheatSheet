### Scalar Types

| Type     | Description                          | Example                                          |
|----------|--------------------------------------|--------------------------------------------------|
| `i8`     | 8-bit signed integer                 | `let x: i8 = -128;`                              |
| `i16`    | 16-bit signed integer                | `let x: i16 = 32767;`                            |
| `i32`    | 32-bit signed integer                | `let x: i32 = 2147483647;`                       |
| `i64`    | 64-bit signed integer                | `let x: i64 = 9223372036854775807;`              |
| `i128`   | 128-bit signed integer               | `let x: i128 = 170141183460469231731687303715884105727;` |
| `isize`  | Architecture-specific signed integer | `let x: isize = -42;`                            |
| `u8`     | 8-bit unsigned integer               | `let x: u8 = 255;`                               |
| `u16`    | 16-bit unsigned integer              | `let x: u16 = 65535;`                            |
| `u32`    | 32-bit unsigned integer              | `let x: u32 = 4294967295;`                       |
| `u64`    | 64-bit unsigned integer              | `let x: u64 = 18446744073709551615;`             |
| `u128`   | 128-bit unsigned integer             | `let x: u128 = 340282366920938463463374607431768211455;` |
| `usize`  | Architecture-specific unsigned integer | `let x: usize = 42;`                             |
| `f32`    | 32-bit floating-point                | `let x: f32 = 3.14;`                             |
| `f64`    | 64-bit floating-point                | `let x: f64 = 3.141592653589793;`                |
| `bool`   | Boolean value (`true` or `false`)    | `let x: bool = true;`                            |
| `char`   | Unicode scalar value (4 bytes)       | `let x: char = 'a';`                             |

### Compound Types

| Type     | Description                          | Example                                          |
|----------|--------------------------------------|--------------------------------------------------|
| `tuple`  | Collection of values of different types | `let tup: (i32, f64, u8) = (500, 6.4, 1);`       |
| `array`  | Collection of values of the same type with a fixed length | `let arr: [i32; 3] = [1, 2, 3];`                 |

### Slices

| Type     | Description                          | Example                                          |
|----------|--------------------------------------|--------------------------------------------------|
| `&[T]`   | Reference to a sequence of elements in a collection | `let slice: &[i32] = &arr[0..2];`                |

### String Types

| Type     | Description                          | Example                                          |
|----------|--------------------------------------|--------------------------------------------------|
| `&str`   | Reference to a string                | `let s: &str = "hello";`                         |
| `String` | Growable, heap-allocated string      | `let mut s: String = String::from("hello"); s.push_str(" world!");` |

### References

| Type     | Description                          | Example                                          |
|----------|--------------------------------------|--------------------------------------------------|
| `&T`     | Allows you to refer to some value without taking ownership | `let r: &i32 = &x;`                              |

### Functions

| Type     | Description                          | Example                                          |
|----------|--------------------------------------|--------------------------------------------------|
| `fn`     | Function type                        | `fn add(x: i32, y: i32) -> i32 { x + y }`        |

### The Unit Type

| Type     | Description                          | Example                                          |
|----------|--------------------------------------|--------------------------------------------------|
| `()`     | Represents an empty value or a value with no information | `let x: () = ();`                                |
