# starlight-time

A simple time and date utility library for **JavaScript** and **Starlight**, providing current time, formatting, timers, and sleep functionality.

---

## Installation

Install via npm:

```bash
npm install starlight-time@latest
```

---

## Import

For both **JavaScript** and **Starlight**:

```js
import time from "starlight-time";
```

---

## Get Current Date and Time

```js
console.log(time.now());          // Current date object
console.log(time.formatDate());   // e.g., "2026-01-12"
console.log(time.formatTime());   // e.g., "14:35:42"
```

**Starlight:**

```sl
sldeploy(time.now());
sldeploy(time.formatDate());
sldeploy(time.formatTime());
```

---

## Sleep / Delay

```js
console.log("Start");
time.sleep(1000);   // Sleep for 1 second
console.log("End");
```

**Starlight:**

```sl
sldeploy("Start");
time.sleep(1000);
sldeploy("End");
```

> ⚠ Note: `sleep` in this version is **blocking**. Use carefully in loops.

---

## Set a Timer

```js
const stop = time.setTimer(() => console.log("Tick"), 1000); // every 1 second

setTimeout(() => {
    stop(); // stop after 5 seconds
    console.log("Timer stopped");
}, 5000);
```

**Starlight:**

```sl
const stop = time.setTimer(() => sldeploy("Tick"), 1000);

setTimeout(() => {
    stop();
    sldeploy("Timer stopped");
}, 5000);
```

> In Starlight, `sldeploy()` is used instead of `print()`.

---

## Convert Seconds to HH:MM:SS

```js
console.log(time.secondsToHMS(3661)); // "01:01:01"
console.log(time.secondsToHMS(59));   // "00:00:59"
```

**Starlight:**

```sl
sldeploy(time.secondsToHMS(3661));
sldeploy(time.secondsToHMS(59));
```

---

## Notes

* All functions are **synchronous**, except timers which use `setInterval`.
* Use **`sldeploy()`** in Starlight for output instead of `console.log()`.
* `sleep` blocks the main thread. For async/non-blocking delays, consider using `await sleepAsync(ms)` (you could add a Promise-based sleep).


