# Operators Reference

## 1. **Arithmetic Operators**

| Operator | Type   | Notes                      |
| -------- | ------ | -------------------------- |
| `+`      | Binary | Addition                   |
| `-`      | Binary | Subtraction                |
| `*`      | Binary | Multiplication             |
| `/`      | Binary | Division                   |
| `%`      | Binary | Modulo                     |
| `+`      | Unary  | Unary plus                 |
| `-`      | Unary  | Unary minus                |
| `++`     | Unary  | Increment (prefix/postfix) |
| `--`     | Unary  | Decrement (prefix/postfix) |

---

## 2. **Assignment Operators**

| Operator | Type                | Notes               |
| -------- | ------------------- | ------------------- |
| `=`      | Assignment          | Assign value        |
| `+=`     | Compound Assignment | Add and assign      |
| `-=`     | Compound Assignment | Subtract and assign |
| `*=`     | Compound Assignment | Multiply and assign |
| `/=`     | Compound Assignment | Divide and assign   |
| `%=`     | Compound Assignment | Modulo and assign   |

---

## 3. **Comparison Operators**

| Operator | Type   | Notes                 |
| -------- | ------ | --------------------- |
| `==`     | Binary | Equals                |
| `!=`     | Binary | Not equal             |
| `<`      | Binary | Less than             |
| `<=`     | Binary | Less than or equal    |
| `>`      | Binary | Greater than          |
| `>=`     | Binary | Greater than or equal |

---

## 4. **Logical Operators**

| Operator | Type   | Notes              |        |            |
| -------- | ------ | ------------------ | ------ | ---------- |
| `&&`     | Binary | Logical AND        |        |            |
| `        |        | `                  | Binary | Logical OR |
| `!`      | Unary  | Logical NOT        |        |            |
| `??`     | Binary | Nullish coalescing |        |            |

---

## 5. **Conditional / Ternary**

| Operator | Type    | Notes                  |
| -------- | ------- | ---------------------- |
| `? :`    | Ternary | Conditional expression |

---

## 6. **Arrow / Lambda Operators**

| Operator | Type  | Notes                      |
| -------- | ----- | -------------------------- |
| `=>`     | Arrow | Arrow function             |
| `->`     | Arrow | Arrow function alternative |

---

## 7. **Member and Index Access**

| Operator | Type   | Notes                    |
| -------- | ------ | ------------------------ |
| `.`      | Member | Object property access   |
| `[]`     | Index  | Array or object indexing |

---

## 8. **Special / Function Operators**

| Operator | Type  | Notes                         |
| -------- | ----- | ----------------------------- |
| `new`    | Unary | Instantiate object/class      |
| `await`  | Unary | Await asynchronous expression |
| `ask()`  | Call  | Prompt for user input         |

---

## 9. **Precedence Overview (High → Low)**

1. Postfix: `++ --`
2. Unary: `+ - ! await new`
3. Multiplicative: `* / %`
4. Additive: `+ -`
5. Comparison: `< <= > >=`
6. Equality: `== !=`
7. Logical AND: `&&`
8. Logical OR: `||`
9. Nullish Coalescing: `??`
10. Conditional / Ternary: `? :`
11. Assignment / Compound Assignment: `= += -= *= /= %=`
12. Arrow Functions: `=> ->`

