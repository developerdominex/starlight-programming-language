# Variables

Variables are containers for storing data. They can hold numbers, strings, arrays, objects, or functions.

---

## 1. Declaring Variables

### `let` – block-scoped variable

```sl
let x = 10;
let name = "Alice";
```

* Must be initialized when declared.
* Can be reassigned later:

```sl
x = 20;
name = "Bob";
```

---

### `define` – global or constant-like variable

```sl
define PI = 3.14159;
define greeting = "Hello!";
```

* Creates a globally accessible variable.
* Can optionally be initialized with a value.
* If you try to redefine an existing `define` in the same scope, it updates the value.

---

## 2. Variable Types

Variables can hold different types of values:

| Type    | Example                       |
| ------- | ----------------------------- |
| Number  | `let age = 25;`               |
| String  | `let name = "Alice";`         |
| Boolean | `let isActive = true;`        |
| Null    | `let empty = null;`           |
| Array   | `let arr = [1, 2, 3];`        |
| Object  | `let obj = { key: "value" };` |

---

## 3. Variable Scope

* **Block scope (`let`)**: Visible only inside the block it was defined.

```sl
if (true) {
  let x = 5;
}
sldeploy(x); // Error: undefined variable
```

* **Global (`define`)**: Accessible from anywhere.

```sl
define y = 10;
if (true) {
  sldeploy(y); // 10
}
```

* **Function scope**: Variables declared inside functions are local.

```sl
func test() {
  let localVar = 42;
  sldeploy(localVar); // 42
}
sldeploy(localVar); // Error: undefined variable
```

---

## 4. Dynamic Typing

Variables can change types after assignment:

```sl
let x = 10;
sldeploy(x); // 10

x = "hello";
sldeploy(x); // "hello"
```

---

## 5. Accessing Variables

* **Simple access**

```sl
let a = 5;
sldeploy(a); // 5
```

* **Objects**

```sl
let person = { "name": "Alice", "age": 20 };
sldeploy(person.name); // "Alice"
```

* **Arrays**

```sl
let nums = [1, 2, 3];
sldeploy(nums[0]); // 1
```

---

## 6. Best Practices

* Use `let` for most variables.
* Use `define` for global or constant values.
* Always initialize variables to avoid runtime errors.
* Use descriptive names to avoid accidental conflicts.

---

This covers everything about variables: **declaration, types, scope, and access**.
