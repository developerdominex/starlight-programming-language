# getting started with starlight

starlight is a simple programming language designed to be easy to learn and fun to use.

## running starlight

to run a file, use:

```

starlight filename.sl
```


to view a markdown file:


```
starlight filename.md
```


## basic syntax

### variables

```sl
let name = "alice"
let age = 16
let is_student = true

sldeploy name
sldeploy age
sldeploy is_student
```

### data types

starlight supports:

* strings: `"hello"`
* numbers: `123`, `3.14`
* booleans: `true`, `false`
* arrays: `[1, 2, 3]`
* objects: `{ key: "value" }`
* functions: `func hello() { ... }`

### operators

```sl
let a = 10
let b = 5

sldeploy a + b
sldeploy a - b
sldeploy a * b
sldeploy a / b
sldeploy a % b

let t = true
let f = false

```

### control flow

```sl
# if statement
if a > b {
    sldeploy "a is greater"
} else {
    sldeploy "b is greater or equal"
}

# while loop
let i = 0
while i < 3 {
    sldeploy i
    i += 1
}

# for loop
for let j = 0; j < 3; j += 1 {
    sldeploy j
}
```

### functions

```sl
func greet(name) {
    sldeploy "hello " + name
}

greet("bob")

# arrow functions
let square = (x) => x * x
sldeploy square(5)
```

### async / await

```sl
func getData(url) async {
    let res = await fetch(url)
    let data = await res.json()
    return data
}

let info = await getData("https://jsonplaceholder.typicode.com/todos/1")
sldeploy info
```

### sldeploy

use `sldeploy` to output values:

```sl
let message = "hello world"
sldeploy message
```

it can display numbers, strings, booleans, arrays, objects, and functions.

