# Introduction to Starlight

Starlight is a **high-level scripting language** designed to be simple, expressive, and versatile. It combines the flexibility of dynamic typing with familiar programming structures.

## Basic Principles

* Everything is a **value**: numbers, strings, booleans, arrays, objects, functions, and more.
* Variables are declared with `let`.
* Statements end automatically; no semicolons are required.
* Functions are first-class citizens and can be assigned to variables or stored in objects.
* Starlight supports asynchronous operations like `fetch` and `sleep`.

## Declaring Variables

Use `let` to declare a variable:

```sl
let name = "Alice"
let age = 25
let isStudent = true
```

Variables can hold any type of value, and the type can change dynamically:

```sl
let data = 10
data = "Now I'm a string"
```

## Data Types

Starlight has several core types:

* **Numbers**: `42`, `3.14`, `-7`
* **Strings**: `"Hello, world!"`
* **Booleans**: `true`, `false`
* **Arrays**: `[1, 2, 3]`, `[ "a", "b" ]`
* **Objects**: `{ "key": "value", "num": 10 }`
* **Functions**: `(x) => x * 2` or named function declarations
* **Null/None**: `null` (no value)

## Operators

* Arithmetic: `+`, `-`, `*`, `/`, `%`
* Comparison: `==`, `!=`, `<`, `<=`, `>`, `>=`
* Logical: `and`, `or`, `not`, `??` (nullish coalescing)
* Assignment: `=`, `+=`, `-=`, `*=`, `/=`, `%=`

## Control Flow

* Conditional statements:

```sl
if age >= 18 {
  let status = "Adult"
} else {
  let status = "Minor"
}
```

* Loops:

```sl
for let i = 0; i < 5; i++ {
  # do something
}

let numbers = [1, 2, 3]
for num in numbers {
  # iterate over array
}
```

* `while` loops:

```sl
let count = 0
while count < 5 {
  count += 1
}
```

## Functions

Functions can be declared or assigned to variables:

```sl
let greet = (name) => "Hello " + name

let result = greet("Alice")  # "Hello Alice"
```

Named function declaration:

```sl
define sayHi(name) {
  "Hi " + name
}
```

## Built-in Utilities

* `print(value)` — output to console
* `len(value)` — get length of array, string, or object
* `keys(obj)` — get object keys
* `values(obj)` — get object values
* `map(array, fn)` — transform array
* `filter(array, fn)` — filter array
* `reduce(array, fn, initial)` — reduce array to a single value
* `ask(prompt)` — get user input
* `sleep(ms)` — pause execution

---

Starlight is designed to **be readable, flexible, and powerful**, while keeping syntax simple and natural.

