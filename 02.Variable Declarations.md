## Two Ways to Declare Variables

1. **`var`** → same as in JavaScript
2. **`let`** → introduced in ES6, preferred in TypeScript

---

## Example with `var`

```ts
function doSomething() {
    for (var i = 0; i < 5; i++) {
        console.log(i);
    }
    console.log('finally ' + i);
}

doSomething();
```

### Output

```
0
1
2
3
4
finally 5
```

---


## Why This Happens with `var`

* In JavaScript, a variable declared with **`var`** is scoped to the **nearest function** (function scope).
* In this case:

  * `i` is declared inside the `for` loop,
  * but it is accessible **anywhere in the `doSomething()` function**.

> This can cause **unexpected behavior**.

---

## Example with `let`

```ts
function doSomething() {
    for (let i = 0; i < 5; i++) {
        console.log(i);
    }
    console.log('finally ' + i); // ❌ Error
}

doSomething();
```

### What Happens

* TypeScript immediately shows a **compile-time error**:

```
Cannot find name 'i'
```

* Because `let` is **block-scoped**, `i` only exists **inside the for-loop block**.
* This prevents accidental usage outside of its intended scope.

---

## Compilation Behavior

* Even if TypeScript reports a **compile-time error**, it still generates JavaScript.

```bash
tsc main.ts
dir
```

Result: `main.js`

---

### Generated `main.js`

```js
function doSomething() {
    for (var i = 0; i < 5; i++) {
        console.log(i);
    }
    console.log('finally ' + i);
}
doSomething();
```

* By default, TypeScript compiles to **ES5 JavaScript** (for maximum browser compatibility).
* ES5 does not support `let`, so the compiler transpiles it back to `var`.
* That’s why running `node main.js` still works and produces the same output.

---


## Summary

* Always **prefer `let`** (or `const`) instead of `var`.
* `let` is **block-scoped**, safer, and avoids many bugs.
* TypeScript:

  * Reports errors at compile time (helps us catch issues early).
  * Still generates valid JavaScript (ensures compatibility).

---


