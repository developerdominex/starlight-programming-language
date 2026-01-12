# starlight-fs

A simple **file system utility** for **JavaScript** and **Starlight**, providing convenient methods for reading, writing, copying, deleting files and directories, as well as path utilities.

---

## Installation

Install via npm:

```bash
npm install starlight-fs@latest
```

---

## Import

For both **JavaScript** and **Starlight**:

```js
import fs from "starlight-fs";
```

---

## File Operations

### Read File

```js
const content = fs.readFile("example.txt");
console.log(content);
```

**Starlight:**

```sl
sldeploy(fs.readFile("example.txt"));
```

---

### Write File

```js
fs.writeFile("example.txt", "Hello Starlight!");
```

**Starlight:**

```sl
fs.writeFile("example.txt", "Hello Starlight!");
```

---

### Append File

```js
fs.appendFile("example.txt", "\nAppended line");
```

**Starlight:**

```sl
fs.appendFile("example.txt", "\nAppended line");
```

---

### Read / Write JSON

```js
const data = fs.readJSON("data.json");
fs.writeJSON("data.json", { name: "Starlight", version: 1 });
```

**Starlight:**

```sl
sldeploy(fs.readJSON("data.json"));
fs.writeJSON("data.json", { name: "Starlight", version: 1 });
```

---

### Delete File

```js
fs.deleteFile("example.txt");
```

**Starlight:**

```sl
fs.deleteFile("example.txt");
```

---

## Directory Operations

### Check if File/Dir Exists

```js
console.log(fs.exists("example.txt")); // true or false
```

**Starlight:**

```sl
sldeploy(fs.exists("example.txt"));
```

---

### Make Directory

```js
fs.makeDir("myFolder");
```

**Starlight:**

```sl
fs.makeDir("myFolder");
```

---

### List Directory Contents

```js
console.log(fs.listDir("myFolder"));
```

**Starlight:**

```sl
sldeploy(fs.listDir("myFolder"));
```

---

### Delete Directory

```js
fs.deleteDir("myFolder");
```

**Starlight:**

```sl
fs.deleteDir("myFolder");
```

---

### Copy File / Directory

```js
fs.copyFile("source.txt", "dest.txt");
fs.copyDir("srcFolder", "destFolder");
```

**Starlight:**

```sl
fs.copyFile("source.txt", "dest.txt");
fs.copyDir("srcFolder", "destFolder");
```

---

## Path Utilities

```js
console.log(fs.join("folder", "file.txt"));   // "folder/file.txt"
console.log(fs.basename("/path/to/file.txt")); // "file.txt"
console.log(fs.dirname("/path/to/file.txt"));  // "/path/to"
console.log(fs.extname("file.txt"));           // ".txt"
console.log(fs.resolve("folder", "file.txt"));
console.log(fs.relative("/a/b", "/a/b/c/d"));  // "c/d"
```

**Starlight:**

```sl
sldeploy(fs.join("folder", "file.txt"));
sldeploy(fs.basename("/path/to/file.txt"));
sldeploy(fs.dirname("/path/to/file.txt"));
sldeploy(fs.extname("file.txt"));
sldeploy(fs.resolve("folder", "file.txt"));
sldeploy(fs.relative("/a/b", "/a/b/c/d"));
```

---

## Notes

* All methods are **synchronous**.
* Use **`sldeploy()`** in Starlight for printing outputs instead of `console.log()`.
* Recursive operations like `copyDir` and `deleteDir` handle nested directories automatically.

