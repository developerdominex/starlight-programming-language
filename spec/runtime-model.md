# Runtime Model

## 1. **Program Execution**

* A program is represented as a **`Program` node** in the AST:

  ```js
  { type: 'Program', body: [ ...statements ] }
  ```
* Execution starts from the top and proceeds **statement by statement**.
* Statements can produce values, alter state, or control flow.

---

## 2. **Values and Types**

Your language has the following **primitive types**:

| Type             | Description                  | Example                  |
| ---------------- | ---------------------------- | ------------------------ |
| `number`         | Integer or floating-point    | `42`, `3.14`             |
| `string`         | Text literal                 | `"hello"`, `'world'`     |
| `boolean`        | `true` or `false`            | `true`, `false`          |
| `null`           | Null value                   | `null`                   |
| `array`          | Ordered collection of values | `[1, 2, 3]`              |
| `object`         | Key-value mapping            | `{ x: 10, y: 20 }`       |
| `function`       | Callable code block          | `func(x) { return x+1 }` |
| `async function` | Asynchronous function        | `async func() { ... }`   |
| `awaitable`      | Result of async operations   | `await fetchData()`      |

---

## 3. **Variables and Scope**

* **Declaration**: `let` creates a block-scoped variable.

  ```js
  let x = 5;
  ```
* **Define**: `define` creates a global or persistent binding.
* **Shadowing**: Inner scopes can shadow variables from outer scopes.
* **Scope types**:

  * **Global**: top-level program or module scope.
  * **Function**: each function has its own local scope.
  * **Block**: scopes inside `{ ... }`.

---

## 4. **Expressions and Evaluation**

Expressions are evaluated according to **operator precedence**:

1. **Postfix:** `++ --`
2. **Unary:** `+ - ! await new`
3. **Multiplicative:** `* / %`
4. **Additive:** `+ -`
5. **Comparison:** `< <= > >=`
6. **Equality:** `== !=`
7. **Logical AND:** `&&`
8. **Logical OR:** `||`
9. **Nullish Coalescing:** `??`
10. **Conditional / Ternary:** `? :`
11. **Assignment:** `= += -= *= /= %=`
12. **Arrow Functions:** `=> ->`

---

## 5. **Functions**

* **Declaration**:

  ```js
  func add(a, b) { return a + b; }
  ```
* **Arrow functions**:

  ```js
  (x) => x + 1
  ```
* **Async functions**: return **awaitable promises**.
* **Calling functions** evaluates arguments and creates a new **local scope**.

---

## 6. **Control Flow**

* **Conditional statements**:

  ```js
  if (condition) { ... } else { ... }
  ```
* **Loops**:

  * `while`, `for`, `do ... track`, `start ... race`
* **Break / Continue** control loop execution.
* **Return** exits a function with a value.

---

## 7. **Special Statements**

| Statement        | Runtime Behavior                                            |
| ---------------- | ----------------------------------------------------------- |
| `sldeploy`       | Executes a special deploy action with evaluated expression. |
| `ask()`          | Prompts for user input and returns value.                   |
| `start { race }` | Executes multiple concurrent blocks, chooses winner.        |
| `do ... track`   | Executes a block with an optional error handling block.     |

---

## 8. **Objects and Arrays**

* **Array**:

  ```js
  [1, 2, 3]
  ```

  * Indexed starting at `0`.
  * Supports dynamic resizing and assignment.
* **Object**:

  ```js
  { key: value }
  ```

  * Keys are strings.
  * Property access via dot (`obj.key`) or index (`obj['key']`).

---

## 9. **Operators**

* Supports **arithmetic**, **comparison**, **logical**, **assignment**, **nullish coalescing**, **member access**, **arrow functions**.
* **Compound assignments** update variables in place (`+= -= *= /= %=`).

---

## 10. **Errors and Exceptions**

* **ParseError**: Syntax errors during parsing.
* **LexerError**: Invalid token or character during lexing.
* **RuntimeError** (to be implemented): Errors during evaluation (division by zero, undefined variable, invalid operations).

---

## 11. **Modules and Imports**

* `import` supports:

  * **Default imports**
  * **Named imports**
  * **Namespace imports**
* Imports are evaluated at runtime to bring values into scope.

---

## 12. **Asynchronous Execution**

* `async func` returns a promise.
* `await` pauses execution until the promise resolves.
* Async functions can be combined with `start { race }` for concurrency.

