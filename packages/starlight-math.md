# starlight-math

A lightweight math utility library for **JavaScript** and **Starlight**, providing constants, functions, and basic vector/matrix operations.

## Installation

Install via npm:

```bash
npm install starlight-math@latest
```

---

## Import

For both **JavaScript** and **Starlight**:

```js
import math from "starlight-math";
```

---

## Constants

```js
console.log(math.pi);           // 3.141592653589793
console.log(math.e);            // 2.718281828459045
console.log(math.phi);          // 1.61803398875
```

**Starlight:**

```sl
sldeploy(math.pi);
sldeploy(math.e);
sldeploy(math.phi);
```

---

## Basic Functions

```js
console.log(math.abs(-5));      // 5
console.log(math.sqrt(16));     // 4
console.log(math.pow(2, 3));    // 8
console.log(math.round(4.6));   // 5
console.log(math.floor(4.9));   // 4
console.log(math.ceil(4.1));    // 5
console.log(math.max(1,2,3));   // 3
console.log(math.min(1,2,3));   // 1
```

**Starlight:**

```sl
sldeploy(math.abs(-5));
sldeploy(math.sqrt(16));
sldeploy(math.pow(2, 3));
sldeploy(math.round(4.6));
sldeploy(math.floor(4.9));
sldeploy(math.ceil(4.1));
sldeploy(math.max([1,2,3])); // pass array instead of arguments if needed
sldeploy(math.min([1,2,3]));
```

---

## Trigonometric Functions

```js
console.log(math.sin(Math.PI/2)); // 1
console.log(math.cos(0));         // 1
console.log(math.tan(Math.PI/4)); // 1
console.log(math.asin(1));        // 1.5707963267948966
console.log(math.acos(0));        // 1.5707963267948966
console.log(math.atan(1));        // 0.7853981633974483
console.log(math.atan2(1, 1));    // 0.7853981633974483
```

**Starlight:**

```sl
sldeploy(math.sin(math.pi / 2));
sldeploy(math.cos(0));
sldeploy(math.tan(math.pi / 4));
sldeploy(math.asin(1));
sldeploy(math.acos(0));
sldeploy(math.atan(1));
sldeploy(math.atan2(1,1));
```

---

## Logarithms

```js
console.log(math.log(10));   // natural log
console.log(math.log10(100));// base 10
console.log(math.log2(8));   // base 2
```

**Starlight:**

```sl
sldeploy(math.log(10));
sldeploy(math.log10(100));
sldeploy(math.log2(8));
```

---

## Random Numbers

```js
console.log(math.random());        // random between 0 and 1
console.log(math.random(5, 10));  // random between 5 and 10
```

**Starlight:**

```sl
sldeploy(math.random());
sldeploy(math.random(5, 10));
```

---

## Factorials, Combinations, Permutations

```js
console.log(math.factorial(5));   // 120
console.log(math.nCr(5, 2));      // 10
console.log(math.nPr(5, 2));      // 20
```

**Starlight:**

```sl
sldeploy(math.factorial(5));
sldeploy(math.nCr(5, 2));
sldeploy(math.nPr(5, 2));
```

---

## Vector Operations

```js
const v1 = [1,2,3];
const v2 = [4,5,6];

console.log(math.vectorAdd(v1, v2));   // [5,7,9]
console.log(math.vectorSub(v1, v2));   // [-3,-3,-3]
console.log(math.vectorDot(v1, v2));   // 32
console.log(math.vectorCross(v1, v2)); // [-3,6,-3]
```

**Starlight:**

```sl
sldeploy(math.vectorAdd([1,2,3], [4,5,6]));
sldeploy(math.vectorSub([1,2,3], [4,5,6]));
sldeploy(math.vectorDot([1,2,3], [4,5,6]));
sldeploy(math.vectorCross([1,2,3], [4,5,6]));
```

---

## Matrix Operations

```js
const A = [[1,2],[3,4]];
const B = [[5,6],[7,8]];

console.log(math.matrixAdd(A, B));       // [[6,8],[10,12]]
console.log(math.matrixSub(A, B));       // [[-4,-4],[-4,-4]]
console.log(math.matrixTranspose(A));    // [[1,3],[2,4]]
```

**Starlight:**

```sl
sldeploy(math.matrixAdd([[1,2],[3,4]], [[5,6],[7,8]]));
sldeploy(math.matrixSub([[1,2],[3,4]], [[5,6],[7,8]]));
sldeploy(math.matrixTranspose([[1,2],[3,4]]));
```

---

✅ **Notes:**

* Starlight requires **`sldeploy()`** instead of `print()` for output.
* When passing object parameters in Starlight, always use **string keys** if required by functions.

