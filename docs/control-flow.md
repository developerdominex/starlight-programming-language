# starlight control flow

starlight provides standard control flow statements like `if`, `else`, `while`, `for`, `for-in`, `break`, `continue`, and custom `start`/`race`/`do and track` for advanced flow control.

---

## if / else

```sl
let x = 10

if x > 5 {
    sldeploy "x is greater than 5"
} else {
    sldeploy "x is 5 or less"
}
```

* `if` requires a boolean condition.
* `else` is optional.
* conditions must evaluate to true/false.

---

## while

```sl
let count = 0

while count < 3 {
    sldeploy count
    count += 1
}
```

* loops run while condition is true.
* use `break` to exit early, `continue` to skip to next iteration.

---

## for

```sl
for let i = 0; i < 3; i += 1 {
    sldeploy i
}
```

* classic `for` loop with initializer, test, and update.
* supports `break` and `continue`.

---

## for-in

```sl
let arr = [10, 20, 30]

for val in arr {
    sldeploy val
}

let obj = {a: 1, b: 2}

for key in obj {
    sldeploy key
}
```

* iterates over arrays or object keys.
* `val` or `key` is dynamically assigned each iteration.

---

## break / continue

```sl
let i = 0

while true {
    i += 1
    if i == 3 {
        break
    }
    if i == 1 {
        continue
    }
    sldeploy i
}
```

* `break` exits the nearest loop.
* `continue` skips the rest of the current iteration.

---

## start / race

```sl
let choice = "b"

start choice {
    race "a" {
        sldeploy "you chose a"
    }
    race "b" {
        sldeploy "you chose b"
    }
    race "c" {
        sldeploy "you chose c"
    }
}
```

* `start` evaluates a discriminant.
* executes the matching `race` clause.
* `break` inside a `race` stops executing further races.

---

## doTrack

```sl
do {
    let x = 10 / 0
} track {
    sldeploy "error caught"
}
```

## tips

* loops and conditional bodies can have multiple statements.
* you can nest any control flow statements.
* `sldeploy` is used for output instead of `print`.
* `start` / `race` / `do and track` are unique to starlight for choice and error handling.

