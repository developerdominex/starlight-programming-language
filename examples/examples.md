# SL Language Examples

## 1. Variables and Data Types

```sl
let x = 42;
let pi = 3.14;
let name = "Alice";
let flag = true;
let nothing = null;

sldeploy x;       # 42
sldeploy pi;      # 3.14
sldeploy name;    # "Alice"
sldeploy flag;    # true
sldeploy nothing; # None
```

---

## 2. Arithmetic

```sl
let a = 5 + 2 * 3;
let b = a - 4 / 2;
let c = 10 % 3;

a += 2;
b *= 3;

sldeploy a; # 13
sldeploy b; # 21
sldeploy c; # 1
```

---

## 3. Logical Expressions

```sl
let x = true && false || true;
let y = null ?? "default";
let z = (a > b) ? a : b;

sldeploy x; # true
sldeploy y; # "default"
sldeploy z; # 21
```

---

## 4. Control Flow

```sl
if (x) {
  sldeploy "x is true";
} else {
  sldeploy "x is false";
}

while (a < 20) {
  a++;
}

for (let i = 0; i < 5; i++) {
  sldeploy i;
}

do {
  sldeploy "Try risky operation";
} track {
  sldeploy "Caught an error";
}
```

---

## 5. Functions

```sl
func add(a, b) {
  return a + b;
}

let double = (x) => x * 2;

async func fetchValue() {
  let input = await ask("Enter a number:");
  return num(input) * 2;
}

sldeploy add(3, 4);       # 7
sldeploy double(5);       # 10
```

---

## 6. Objects and Arrays

```sl
let nums = [1, 2, 3, 4];
let obj = { x: 10, y: 20 };

sldeploy nums[0];   # 1
sldeploy obj.x;     # 10

nums[0] = 42;
obj.z = 99;

sldeploy nums;      # [42, 2, 3, 4]
sldeploy obj;       # { x: 10, y: 20, z: 99 }
```

---

## 7. Looping with `for-in` and `range`

```sl
for i in [10, 20, 30] {
  sldeploy i;
}

for key in {a:1, b:2} {
  sldeploy key; # a, b
}

for i in range(1, 5) {
  sldeploy i; # 1,2,3,4
}
```

---

## 8. Async / Await and Concurrency

```sl
async func task(name) {
  await sleep(500);
  sldeploy name;
}

start {
  race task("First");
  race task("Second");
}
```

---

## 9. Built-in Functions

```sl
sldeploy len([1,2,3]);       # 3
sldeploy len({a:1, b:2});    # 2
sldeploy type([1,2]);        # "array"
sldeploy keys({x:10, y:20}); # ["x","y"]
sldeploy values({x:10, y:20}); # [10,20]

let nums = [1,2,3,4];
let doubled = await map(nums, (x) => x*2);
let evens = await filter(nums, (x) => x % 2 === 0);
let sum = await reduce(nums, (a,b) => a+b, 0);

sldeploy doubled; # [2,4,6,8]
sldeploy evens;   # [2,4]
sldeploy sum;     # 10
```

---

## 10. Importing Modules

```sl
import "utils.sl";

import { add, subtract } from "math.sl";

import * as lib from "library";

sldeploy add(3,4);
```

---

## 11. Error Handling

```sl
do {
  let x = 10 / 0;
} track {
  sldeploy "Division error caught!";
}

let a;
try {
  sldeploy a.b; # null access
} track {
  sldeploy "Cannot access property of undefined";
}
```

---

## 12. Update Expressions

```sl
let x = 5;
x++;        # 6
++x;        # 7
x--;        # 6
--x;        # 5

x += 10;    # 15
x *= 2;     # 30
```

---

## 13. Asking User Input

```sl
let name = ask("Enter your name:");
sldeploy "Hello, " + name;
```

