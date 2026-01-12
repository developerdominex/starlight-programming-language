# async / await in Starlight

your language supports asynchronous programming using `async` functions and the `await` keyword. this allows you to write non-blocking code that reads like normal synchronous code.

## declaring async functions

use the `async func` syntax to define an asynchronous function:

```sl
async func fetchdata(url) {
    let response = await fetch(url);
    let data = await response.json();
    return data;
}
```

* `async func` marks the function as asynchronous.
* inside an `async` function, you can use `await` to pause execution until a promise-like operation completes.
* returning a value from an async function automatically wraps it as a "resolved async result".

## using `await`

`await` can be used with any async operation:

```sl
async func main() {
    let user = await get('https://api.example.com/user/1');
    sldeploy user;
}

main();  // calling an async function
```

* `await` can only be used inside `async` functions.
* execution pauses at `await` until the operation resolves.
* the resolved value is returned and can be stored in a variable.

## error handling with `do…track`

use `do…track` to catch errors from async operations:

```sl
async func loaddata() {
    do {
        let data = await fetch('https://api.example.com/data');
        sldeploy await data.json();
    } track {
        sldeploy 'an error occurred:', error;
    }
}
```

* `do` contains the code that might fail.
* `track` handles errors; the `error` variable holds the exception.

## awaiting multiple async calls

you can run multiple async calls sequentially:

```sl
async func process() {
    let a = await fetch('https://api.example.com/a');
    let b = await fetch('https://api.example.com/b');
    sldeploy [await a.json(), await b.json()];
}
```

or process arrays asynchronously:

```sl
async func processusers(users) {
    let results = await map(users, async (u) => {
        let res = await fetch(`https://api.example.com/user/${u.id}`);
        return await res.json();
    });
    sldeploy results;
}
```

* `map`, `filter`, and `reduce` are fully async-aware.
* always `await` async callbacks to maintain proper sequence.

## async arrow functions

async arrow functions work with `await`:

```sl
let fetchuser = async (id) => {
    let response = await fetch(`https://api.example.com/user/${id}`);
    return await response.json();
};

async func run() {
    let user = await fetchuser(1);
    sldeploy user;
}

run();
```

## loops with async/await

you can use async functions inside loops:

```sl
async func loopfetch(users) {
    for let u in users {
        let data = await fetch(`https://api.example.com/user/${u}`);
        sldeploy await data.json();
    }
}
```

or using `for…in` over objects:

```sl
async func objloop(obj) {
    for let key in obj {
        let val = await obj[key];
        sldeploy key, val;
    }
}
```

## sleep and delay

you can pause execution asynchronously:

```sl
async func countdown(n) {
    for let i = n; i > 0; i-- {
        sldeploy i;
        await sleep(1000);  // pause 1 second
    }
    sldeploy 'done!';
}
```

## calling async functions

* you can call async functions from other async functions using `await`.
* calling an async function without `await` gives a "function object" (like a promise).

```sl
async func main() {
    let data = await fetchdata('https://api.example.com');
    sldeploy data;
}

main();
```

## async with error handling in loops

you can combine loops, async, and `do…track`:

```sl
async func safefetch(users) {
    for let u in users {
        do {
            let res = await fetch(`https://api.example.com/user/${u}`);
            sldeploy await res.json();
        } track {
            sldeploy 'failed to fetch user', u, ':', error;
        }
    }
}
```

## summary table

| feature              | syntax example                   | notes                             |
| -------------------- | -------------------------------- | --------------------------------- |
| async function       | `async func name(params) { … }`  | use `await` inside                |
| await expression     | `let x = await asynccall()`      | only inside async                 |
| async arrow function | `let fn = async (params) => …`   | can be single-expression or block |
| error handling       | `do { … } track { … }`           | `error` variable holds exception  |
| async loops          | `for let x in array { await … }` | handles async correctly           |
| async utilities      | `map`, `filter`, `reduce`        | fully async-aware                 |
| sleep / delay        | `await sleep(ms)`                | pauses execution asynchronously   |

