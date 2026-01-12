# Syntax Overview

This is a quick reference for the core syntax and constructs of your language.

---

## 1. Variables

### Declaration

```sl
let x = 10;
let name = "Alice";
```

* `let` declares a new variable.
* Variables must be initialized.

### Definition (global or constant-like)

```sl
define PI = 3.14159;
define greeting = "Hello!";
```

* `define` creates a variable that persists globally.

---

## 2. Data Types

* **Numbers**: `123`, `3.14`
* **Strings**: `"Hello"`, `'World'`
* **Booleans**: `true`, `false`
* **Null**: `null`
* **Arrays**: `[1, 2, 3]`
* **Objects**: `{ key: "value", num: 42 }`

---

## 3. Operators

### Arithmetic

```sl
a + b
a - b
a * b
a / b
a % b
```

### Assignment

```sl
x = 5;
x += 3;  // x = x + 3
x -= 2;
x *= 2;
x /= 4;
x %= 2;
```

### Comparison

```sl
a == b
a != b
a < b
a <= b
a > b
a >= b
```

### Logical

```sl
a && b   // AND
a || b   // OR
a ?? b   // Nullish coalescing
!a       // NOT
```

---

## 4. Control Flow

### If / Else

```sl
if (x > 0) {
  sldeploy("Positive");
} else if (x < 0) {
  sldeploy("Negative");
} else {
  sldeploy("Zero");
}
```

### While Loop

```sl
while (x < 5) {
  sldeploy(x);
  x += 1;
}
```

### For Loop

```sl
for (let i = 0; i < 5; i += 1) {
  sldeploy(i);
}
```

### For-In Loop

```sl
for (let key in obj) {
  sldeploy(key);
}
```

### Do-Track (try-catch-like)

```sl
do {
  sldeploy(10 / 0);
} track {
  sldeploy(error); // error contains the exception
}
```

---

## 5. Functions

### Regular Function

```sl
func add(a, b) {
  return a + b;
}

sldeploy(add(2, 3)); // 5
```

### Async Function

```sl
async func fetchData(url) {
  let response = await get(url);
  return response;
}
```

### Arrow Function

```sl
let square = x => x * x;
sldeploy(square(5)); // 25
```

---

## 6. Start Statement (switch-like)

```sl
start score {
  race 100 {
    sldeploy("Perfect!");
  }
  race 50 {
    sldeploy("Halfway there!");
  }
  race 0 {
    sldeploy("Try again!");
  }
}
```

* `start` evaluates a value.
* `race` defines possible matches.
* Execution begins at the first matching race and continues until break or end.

---

## 7. Arrays & Objects

### Arrays

```sl
let nums = [1, 2, 3];
sldeploy(nums[0]); // 1
```

### Objects

```sl
let person = { name: "Alice", age: 20 };
sldeploy(person.name); // Alice
```

---

## 8. Importing Modules

```sl
import { func1, func2 } from "utils.sl";
import * as utils from "utils.sl";
import defaultFunc from "utils.sl";
```

---

## 9. Built-in Functions

* `sldeploy(value)` → prints a value to the console
* `len(array|string|object)` → returns the length
* `type(value)` → returns the type
* `map(array, fn)`, `filter(array, fn)`, `reduce(array, fn, initial)`
* `keys(obj)`, `values(obj)`
* `range(start, end, step)` → generates an array of numbers
* `ask(prompt)` → gets user input
* `num(value)` → converts to number
* `str(value)` → converts to string
* `sleep(ms)` → delays execution
* `fetch(url)` / `get(url)` / `post(url, data)` → HTTP requests

---

## 10. Miscellaneous

* **Member Access**

```sl
obj.key
obj["key"]
```

* **Function Calls**

```sl
myFunc(1, 2);
```

* **New Object Instantiation**

```sl
let obj = new MyClass(arg1, arg2);
```

* **Update Expressions**

```sl
x++;
--y;
obj.value++;
arr[0]--;
```

---

This document covers all major syntax elements in your language, with `sldeploy` as the primary output mechanism.
