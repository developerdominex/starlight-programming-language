```sl
# functions in starlight

# defining a function
func greet(name) {
    sldeploy "hello " + name
}

# calling a function
greet("alice")

# function returning a value
func add(a, b) {
    return a + b
}

let sum = add(5, 7)
sldeploy sum

# arrow functions (inline)
let multiply = (x, y) => x * y
sldeploy multiply(3, 4)

# arrow function with block
let divide = (a, b) => {
    if b == 0 {
        return "cannot divide by zero"
    }
    return a / b
}

sldeploy divide(10, 2)
sldeploy divide(10, 0)

# functions can be assigned to variables
let fn = greet
fn("bob")

# functions can be passed as arguments
func applyFn(fn, value) {
    return fn(value)
}

let result = applyFn((x) => x * 2, 8)
sldeploy result

# async functions
func asyncFetch(url) async {
    let response = await fetch(url)
    let data = await response.json()
    return data
}

# calling async function
let data = await asyncFetch("https://jsonplaceholder.typicode.com/todos/1")
sldeploy data
```

✅ key points:

* `func name(params) { ... }` defines a function
* `return` sends a value back
* arrow functions `(params) => expr` or `(params) => { ... }` are supported
* functions are first-class: can be stored in variables, passed around
* `async` functions support `await` for promises or async tasks
* `sldeploy` is used for output instead of `print`

