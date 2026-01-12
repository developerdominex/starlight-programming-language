# Arrays in SL

Arrays in SL are **ordered collections** of values. They can contain any type, including numbers, strings, booleans, objects, other arrays, and even functions.

## 1. Creating Arrays

```sl
let nums = [1, 2, 3, 4, 5];
let names = ["Alice", "Bob", "Charlie"];
let mixed = [1, "two", true, null];
let nested = [[1, 2], [3, 4]];
```

---

## 2. Accessing Elements

Array elements are accessed using **zero-based indices**:

```sl
sldeploy nums[0];    # 1
sldeploy names[1];   # "Bob"
sldeploy nested[1][0]; # 3
```

If the index is out of bounds, SL returns `undefined`:

```sl
sldeploy nums[10]; # undefined
```

---

## 3. Modifying Arrays

You can assign new values to existing indices:

```sl
nums[0] = 42;
names[2] = "Charlie Brown";

sldeploy nums;   # [42, 2, 3, 4, 5]
sldeploy names;  # ["Alice", "Bob", "Charlie Brown"]
```

Arrays can grow dynamically by assigning to new indices:

```sl
nums[5] = 6;
sldeploy nums; # [42, 2, 3, 4, 5, 6]
```

---

## 4. Array Operations

SL supports **iteration and higher-order functions**:

```sl
let nums = [1, 2, 3, 4];

# Map: apply a function to each element
let squared = await map(nums, (x) => x * x);
sldeploy squared; # [1, 4, 9, 16]

# Filter: select elements
let evens = await filter(nums, (x) => x % 2 == 0);
sldeploy evens; # [2, 4]

# Reduce: accumulate values
let sum = await reduce(nums, (a, b) => a + b, 0);
sldeploy sum; # 10
```

---

## 5. Iterating Over Arrays

### Using `for` loops

```sl
for (let i = 0; i < nums.length; i++) {
  sldeploy nums[i];
}
```

### Using `for-in` loops

```sl
for n in nums {
  sldeploy n;
}
```

---

## 6. Built-in Functions for Arrays

* `len(array)` — returns the length of the array:

```sl
sldeploy len(nums); # 4
```

* `map(array, fn)` — returns a new array with each element transformed by `fn`.
* `filter(array, fn)` — returns a new array containing elements where `fn` returns `true`.
* `reduce(array, fn, initial)` — reduces the array to a single value using `fn`.

---

## 7. Combining Arrays

Arrays can be nested or concatenated manually:

```sl
let a = [1, 2];
let b = [3, 4];
let c = [a[0], a[1], b[0], b[1]];

sldeploy c; # [1, 2, 3, 4]
```

---

## 8. Summary

* Arrays are **zero-indexed**.
* Can contain **any value type**, including other arrays.
* Support **dynamic assignment**, **iteration**, and **higher-order functions** like `map`, `filter`, `reduce`.
* Use `len()` to get the number of elements.
* Access out-of-bounds indices safely: returns `undefined`.

