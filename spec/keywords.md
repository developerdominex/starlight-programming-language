# Keywords & Tokens Reference 

## 1. **Reserved Keywords**

These are recognized as special tokens and cannot be used as identifiers:

| Keyword    | Token Type |
| ---------- | ---------- |
| `let`      | LET        |
| `sldeploy` | SLDEPLOY   |
| `if`       | IF         |
| `else`     | ELSE       |
| `while`    | WHILE      |
| `for`      | FOR        |
| `break`    | BREAK      |
| `continue` | CONTINUE   |
| `func`     | FUNC       |
| `return`   | RETURN     |
| `true`     | TRUE       |
| `false`    | FALSE      |
| `null`     | NULL       |
| `ask`      | ASK        |
| `define`   | DEFINE     |
| `import`   | IMPORT     |
| `from`     | FROM       |
| `as`       | AS         |
| `async`    | ASYNC      |
| `await`    | AWAIT      |
| `new`      | NEW        |
| `in`       | IN         |
| `do`       | DO         |
| `track`    | TRACK      |
| `start`    | START      |
| `race`     | RACE       |

---

## 2. **Literals**

| Literal Type | Token Type | Example           |
| ------------ | ---------- | ----------------- |
| Number       | NUMBER     | `42`, `3.14`      |
| String       | STRING     | `"hello"`, `'hi'` |
| Boolean      | TRUE/FALSE | `true`, `false`   |
| Null         | NULL       | `null`            |

---

## 3. **Operators**

### Assignment / Compound Assignment

| Symbol | Token Type |
| ------ | ---------- |
| `=`    | EQUAL      |
| `+=`   | PLUSEQ     |
| `-=`   | MINUSEQ    |
| `*=`   | STAREQ     |
| `/=`   | SLASHEQ    |
| `%=`   | MODEQ      |

### Arithmetic

| Symbol | Token Type |
| ------ | ---------- |
| `+`    | PLUS       |
| `-`    | MINUS      |
| `*`    | STAR       |
| `/`    | SLASH      |
| `%`    | MOD        |

### Comparison

| Symbol | Token Type |
| ------ | ---------- |
| `==`   | EQEQ       |
| `!=`   | NOTEQ      |
| `<`    | LT         |
| `<=`   | LTE        |
| `>`    | GT         |
| `>=`   | GTE        |

### Logical

| Symbol | Token Type         |   |    |
| ------ | ------------------ | - | -- |
| `&&`   | AND                |   |    |
| `!`    | NOT                |   |    |
| `??`   | NULLISH_COALESCING |   |    |

### Increment / Decrement

| Symbol | Token Type |
| ------ | ---------- |
| `++`   | PLUSPLUS   |
| `--`   | MINUSMINUS |

### Arrow Function

| Symbol | Token Type |
| ------ | ---------- |
| `=>`   | ARROW      |
| `->`   | ARROW      |

---

## 4. **Punctuation & Delimiters**

| Symbol | Token Type |
| ------ | ---------- |
| `(`    | LPAREN     |
| `)`    | RPAREN     |
| `{`    | LBRACE     |
| `}`    | RBRACE     |
| `[`    | LBRACKET   |
| `]`    | RBRACKET   |
| `;`    | SEMICOLON  |
| `,`    | COMMA      |
| `:`    | COLON      |
| `.`    | DOT        |

---

## 5. **Comments**

| Type        | Syntax          |
| ----------- | --------------- |
| Single-line | `# comment`     |
| Multi-line  | `#* comment *#` |

---

### ✅ Notes:

1. Keywords are case-sensitive and mapped to uppercase token types.
2. Strings support escape sequences like `\n`, `\t`, `\"`, `\'`, `\\`.
3. Number literals can be integers or floats.
4. Multi-character operators (`==`, `!=`, `<=`, `>=`, `&&`, `||`, `??`, `+=`, etc.) are checked **before single-character tokens**.
5. Arrow functions use both `=>` and `->`.

