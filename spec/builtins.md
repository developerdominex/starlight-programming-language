# Built-in Features of Starlight

## Output

### `sldeploy(value)`
Outputs a formatted value to standard output.

- Colors values based on type
- Handles arrays, objects, functions, and circular references

```sl
sldeploy "Hello"
sldeploy [1, 2, 3]
sldeploy { a: 1, b: 2 }
````

---

## Input

### `ask(prompt)`

Reads user input from the terminal.

* Prompt **must** be a string

```sl
let name = ask("Enter your name:")
```

---

## Type & Conversion

### `type(value)`

Returns the runtime type of a value.

```sl
type(10)        // "number"
type("hi")      // "string"
type([1,2])     // "array"
type({})        // "object"
```

---

### `num(value)`

Converts a value to a number.

* Throws a runtime error if conversion fails

```sl
num("42")       // 42
num("abc")      // RuntimeError
```

---

### `str(value)`

Converts a value to a string.

```sl
str(100)        // "100"
```

---

## Collections

### `len(value)`

Returns length of:

* array
* string
* object (number of keys)

```sl
len([1,2,3])    // 3
len("abc")      // 3
len({a:1})      // 1
```

---

### `keys(object)`

Returns an array of object keys.

```sl
keys({a:1, b:2})   // ["a", "b"]
```

---

### `values(object)`

Returns an array of object values.

```sl
values({a:1, b:2}) // [1, 2]
```

---

## Array Utilities

### `map(array, fn)`

Applies a function to each element.

* Supports async functions

```sl
map([1,2,3], x => x * 2)
```

---

### `filter(array, fn)`

Filters array elements.

```sl
filter([1,2,3,4], x => x > 2)
```

---

### `reduce(array, fn, initial?)`

Reduces array to a single value.

```sl
reduce([1,2,3], (a,b) => a + b)
```

---

### `range(...)`

Generates numeric ranges.

```sl
range(5)          // [0,1,2,3,4]
range(1,5)        // [1,2,3,4]
range(10,0,-2)    // [10,8,6,4,2]
```

* Step cannot be `0`
* Throws runtime error on invalid arguments

---

## Async & Time

### `sleep(ms)`

Pauses execution asynchronously.

```sl
await sleep(1000)
```

---

## Networking

### `fetch(url, options?)`

Performs an HTTP request.

Returns an object with:

* `status`
* `ok`
* `text()`
* `json()`

```sl
res = await fetch("https://example.com")
data = await res.json()
```

---

### `get(url)`

HTTP GET request returning parsed JSON.

```sl
data = await get("https://api.example.com")
```

---

### `post(url, data)`

HTTP POST request with JSON body.

```sl
post("https://api.example.com", { a: 1 })
```

---

## Variables

### `let`

Declares a variable **with initializer required**.

```sl
let x = 10
```

---

### `define`

Defines a variable or constant.

```sl
define PI = 3.14
```

---

## Control Flow

### `if / else`

Conditional execution.

```sl
if x > 5 {
  sldeploy "big"
} else {
  sldeploy "small"
}
```

---

### `while`

Loop while condition is true.

```sl
while x < 5 {
  x++
}
```

---

### `for`

Classic loop:

```sl
for let i = 0; i < 5; i++ {
  sldeploy i
}
```

---

### `for ... in`

Iterates over arrays or objects.

```sl
for x in [1,2,3] {
  sldeploy x
}

for k in {a:1, b:2} {
  sldeploy k
}
```

---

### `break`

Exits a loop.

---

### `continue`

Skips current iteration.

---

## Functions

### `func`

Defines a function.

```sl
func add(a, b) {
  return a + b
}
```

---

### `async func`

Defines an async function.

```sl
async func load() {
  await sleep(1000)
}
```

---

### Arrow Functions

```sl
x => x * 2
(a, b) => a + b
```

* Supports expression and block bodies
* Supports async execution

---

### `return`

Returns a value from a function.

---

## Error Handling

### `do / track`

Error-handling construct.

```sl
do {
  risky()
} track {
  sldeploy error
}
```

* `error` is automatically available in `track`

---

## Branch Matching

### `start / race`

Value-based branching.

```sl
start x {
  race 1 {
    sldeploy "one"
  }
  race 2 {
    sldeploy "two"
  }
}
```

---

## Imports

### `import`

Supports **both Starlight files and Node.js modules**.

#### Import Starlight files (`.sl`)

```sl
import x from "math.sl"
import { add } from "math.sl"
import * as math from "math.sl"
```

* `.sl` files are executed
* All defined symbols are exported
* `default` export maps to the module object

#### Import Node.js modules

```sl
import fs from "fs"
import path from "path"
```

* Uses Node.js `require`
* Works with installed npm packages

---

## Expressions & Operators

### Binary Operators

```
+  -  *  /  %
== != < <= > >=
```

---

### Logical Operators

```
&&  ||  ??
```

* `??` is nullish coalescing

---

### Unary Operators

```
!  +  -
```

---

### Update Operators

```
x++
--y
```

---

### Ternary Operator

```sl
x > 5 ? "yes" : "no"
```

---

### Objects

```sl
{ a: 1, b: 2 }
```

* Dynamic property creation allowed

---

### Arrays

```sl
[1, 2, 3]
```

---

### Indexing

```sl
arr[0]
obj["key"]
```

---

### Member Access

```sl
obj.key
```

---

### `new`

Creates an object from a function.

```sl
new MyClass(1, 2)
```

---

### `await`

Waits for async values.

```sl
await fetch(url)
```

---

## Runtime Notes

* Dynamically typed
* Lexical scoping with environments
* Functions are first-class
* Async/await is native
* Detailed runtime errors include line & column
* Variable name suggestions on undefined access

---
