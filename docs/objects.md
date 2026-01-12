# Objects in Your Language

Objects are collections of key-value pairs. They are similar to dictionaries or maps in other languages. Keys can be strings, numbers, or expressions, and values can be any type, including other objects or functions.

## Creating Objects

Objects are created using `let` with curly braces `{}`:

```sl
let myObj = {
  "name": "Alice",
  "age": 25,
  "isStudent": true
}
```

Keys must be unique within an object. Values can be literals, arrays, functions, or even other objects.

## Accessing Properties

Properties of an object can be accessed using **dot notation** or **bracket notation**:

```sl
let name = myObj.name
let age = myObj["age"]
```

You can also assign new values to existing properties:

```sl
myObj.age = 26
myObj["isStudent"] = false
```

New properties can be added dynamically:

```sl
myObj.grade = "A"
```

## Nested Objects

Objects can contain other objects:

```sl
let person = {
  "name": "Bob",
  "address": {
    "city": "New York",
    "zip": "10001"
  }
}

let city = person.address.city
```

## Iterating Over Objects

You can iterate over objects using a **for-in** loop. This iterates over the keys:

```sl
for key in person {
  let value = person[key]
}
```

You can also use built-in functions:

```sl
let keysList = keys(person)       # ["name", "address"]
let valuesList = values(person)   # ["Bob", { "city": "New York", "zip": "10001" }]
```

## Object Methods

Objects can hold functions as values:

```sl
let calculator = {
  "add": (a, b) => a + b,
  "subtract": (a, b) => a - b
}

let sum = calculator.add(5, 3)       # 8
let difference = calculator["subtract"](10, 4)  # 6
```

Functions inside objects behave like normal functions but can also access the object if `this` is used.

## Summary

* Objects store key-value pairs.
* Keys can be accessed via dot `.` or bracket `[]`.
* Objects can be nested and hold any type of value.
* New properties can be added dynamically.
* Iterate over objects with `for-in` or use `keys` and `values`.
* Objects can contain functions as methods.

