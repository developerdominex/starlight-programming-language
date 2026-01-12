# Language Specification

## 1. **Introduction**

This language is a JavaScript-inspired scripting language with custom keywords and syntax for tasks like asynchronous functions, tracking, deployments (`sldeploy`), and race conditions (`start ... race`).
It supports:

* Variables and constants
* Functions (normal and async)
* Control flow (`if`, `while`, `for`, `do...track`, `start...race`)
* Expressions (arithmetic, logical, ternary, assignment)
* Imports, object and array literals

---

## 2. **Lexical Structure**

### 2.1 Whitespace

* Spaces, tabs, and newlines are ignored except for token separation.
* Newlines increment line counters for error reporting.

### 2.2 Comments

| Type        | Syntax          |
| ----------- | --------------- |
| Single-line | `# comment`     |
| Multi-line  | `#* comment *#` |

### 2.3 Identifiers

* Must start with a letter or underscore (`_`)
* Can contain letters, digits, or underscores.
* Example: `myVar`, `_temp1`

### 2.4 Keywords

Reserved words cannot be used as identifiers.

```
let, sldeploy, if, else, while, for, break, continue,
func, return, true, false, null,
ask, define, import, from, as,
async, await, new, in, do, track, start, race
```

### 2.5 Literals

| Type    | Example           |
| ------- | ----------------- |
| Number  | `42`, `3.14`      |
| String  | `"hello"`, `'hi'` |
| Boolean | `true`, `false`   |
| Null    | `null`            |

### 2.6 Operators

#### Assignment / Compound Assignment

```
=, +=, -=, *=, /=, %=
```

#### Arithmetic

```
+, -, *, /, %
```

#### Comparison

```
==, !=, <, <=, >, >=
```

#### Logical

```
&&, ||, !, ??
```

#### Increment / Decrement

```
++, --
```

#### Arrow Function

```
=>, ->
```

### 2.7 Punctuation

```
( ) { } [ ] ; , : .
```

---

## 3. **Expressions**

### 3.1 Primary Expressions

* Literals: numbers, strings, booleans, null
* Identifiers
* Grouped expressions: `(expr)`
* Array literals: `[expr1, expr2, ...]`
* Object literals: `{ key: value, ... }`
* `await expr`
* `new Constructor(args...)`
* `ask(expr...)`

### 3.2 Unary Operators

```
+, -, !, ++, --
```

### 3.3 Binary Operators

* Arithmetic: `+ - * / %`
* Comparison: `< <= > >= == !=`
* Logical: `&& || ??`

### 3.4 Ternary / Conditional

```
condition ? exprIfTrue : exprIfFalse
```

### 3.5 Assignment

```
variable = expr
variable += expr
...
```

### 3.6 Function Calls and Member Access

```
func(arg1, arg2)
obj.property
array[index]
```

### 3.7 Arrow Functions

* Syntax: `(params) => expr` or `(params) -> expr`
* Can have block body: `(params) => { statements }`

---

## 4. **Statements**

### 4.1 Variable Declaration

```
let x = 5;
```

### 4.2 Function Declaration

```
func foo(a, b) { ... }
async func bar() { ... }
```

### 4.3 Control Flow

#### If Statement

```
if (condition) { ... } else { ... }
```

#### While Loop

```
while (condition) { ... }
```

#### For Loop

* Standard:

```
for (init; test; update) { ... }
```

* For-in loop:

```
for (let item in iterable) { ... }
```

#### Do...Track

```
do { ... } track { ... }
```

#### Start...Race

```
start expr {
  race condition1 { ... }
  race condition2 { ... }
}
```

### 4.4 Return

```
return expr;
```

### 4.5 Break / Continue

```
break;
continue;
```

### 4.6 Expression Statement

Any expression can be a statement:

```
x + y;
ask("name");
```

---

## 5. **Imports**

Supports default, named, and namespace imports:

```
import foo from "module";
import { a, b as c } from "module";
import * as ns from "module";
```

---

## 6. **Blocks**

* Enclosed in `{ ... }`
* Can contain multiple statements
* Used in functions, loops, conditionals, etc.

---

## 7. **Error Handling**

* Lexer throws `LexerError` for invalid characters or unterminated strings/comments.
* Parser throws `ParseError` for unexpected tokens or syntax errors.

---

## 8. **Example Program**

```js
async func greet(name) {
  let greeting = ask("Enter greeting:");
  return greeting + ", " + name;
}

start event {
  race ready { sldeploy greet("Alice"); }
  race timeout { sldeploy "Timeout!"; }
}
```

