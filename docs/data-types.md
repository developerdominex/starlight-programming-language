# starlight data types

starlight supports standard data types including numbers, strings, booleans, arrays, objects, functions, and `null` (none).

---

## numbers

```sl
let a = 10
let b = 3.14
let c = -5

sldeploy a
sldeploy b
sldeploy c
```

* all numbers are floating-point compatible.
* arithmetic supports `+`, `-`, `*`, `/`, `%`.

---

## strings

```sl
let str1 = "hello"
let str2 = 'world'
let str3 = str1 + " " + str2

sldeploy str1
sldeploy str3
```

* use `"`.
* concatenation with `+`.

---

## booleans

```sl
let t = true
let f = false

sldeploy t
sldeploy f
```

---

## null / none / undefined

```sl
let n = null
let u = undefined

sldeploy n
sldeploy u
```

* `null` is none.
* `undefined` appears when variables are declared but not assigned.

---

## arrays

```sl
let arr = [1, 2, 3]
let empty = []

sldeploy arr
sldeploy arr[0]
sldeploy len(arr)
```

* dynamic typing allowed.
* can store numbers, strings, booleans, objects, other arrays.

---

## objects

```sl
let obj = {name: "alice", age: 20}

sldeploy obj.name
sldeploy obj["age"]
sldeploy keys(obj)
sldeploy values(obj)
```

* key-value pairs.
* keys are usually strings.
* access via dot `obj.key` or index `obj["key"]`.

---

## functions

```sl
func add(a, b) {
    return a + b
}

let result = add(5, 7)
sldeploy result

let arrow = (x, y) => x * y
sldeploy arrow(3, 4)
```

* declared using `func name(params) {}`.
* arrow functions `(params) => expr` return the expression value.
* functions are first-class: can be passed as arguments or stored in variables.

---

## type checks

```sl
sldeploy type(10)
sldeploy type("hello")
sldeploy type([1,2,3])
sldeploy type({"a":1})
sldeploy type(add)
sldeploy type(null)
```

* returns `number`, `string`, `array`, `object`, `function`, or `boolean`.

---

## tips

* starlight is dynamically typed.
* you can mix data types in arrays and objects.
* use `sldeploy` for output, `len()` for array or string length.
* all standard operations follow javascript-like behavior.

