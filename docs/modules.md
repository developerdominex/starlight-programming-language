# Modules in Starlight

Modules in Starlight allow you to **organize code into separate files** and **reuse functionality** across programs. They help keep your code clean, maintainable, and modular.

## Importing Modules

Use the `import` statement to include another module in your program. You can import specific exports, the default export, or the entire module as a namespace.

### Default Import

```sl
import fs from "./fileUtils.sl"

let content = fs.readFile("data.txt")
```

### Named Import

```sl
import { readFile, writeFile } from "./fileUtils.sl"

let content = readFile("data.txt")
writeFile("output.txt", content)
```

### Namespace Import

```sl
import * as fs from "./fileUtils.sl"

let content = fs.readFile("data.txt")
```

## Exporting from a Module

In Starlight, everything defined in a file can be exported and used in other modules.

### Example: Exporting Named Functions

```sl
define greet(name) {
  "Hello " + name
}

define farewell(name) {
  "Goodbye " + name
}
```

You can then import these functions using a named import:

```sl
import { greet, farewell } from "./messages.sl"

let msg = greet("Alice")   # "Hello Alice"
let bye = farewell("Bob")  # "Goodbye Bob"
```

### Default Export

To export the entire module as a default:

```sl
let defaultExport = {
  greet: greet,
  farewell: farewell
}
```

And import it like this:

```sl
import messages from "./messages.sl"

let msg = messages.greet("Alice")
```

## Importing External Libraries

Starlight can import **Node.js modules** or packages installed via npm:

```sl
import fs from "fs"

let data = fs.readFileSync("data.txt", "utf-8")
```

If a module cannot be found, Starlight will throw a **RuntimeError** with a suggestion if a similar name exists.

## Module Scope

* Each module has its own **environment**.
* Variables and functions defined inside a module are **not global** unless explicitly exported.
* This avoids conflicts and allows safe reuse of code.

## Tips

* Use **named imports** for clarity.
* Use **default exports** for a module that mainly provides one object or function.
* Keep modules **small and focused** on a single task.

---

Modules in Starlight make it easy to **split large programs** into manageable pieces while maintaining clean and reusable code.
