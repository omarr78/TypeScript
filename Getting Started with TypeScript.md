
## 1. Install TypeScript Globally

```bash
npm install -g typescript
```

* `-g` stands for **global** installation.
* This makes the TypeScript compiler (`tsc`) available system-wide.

---

## 2. Verify Installation

```bash
tsc --version
```

* Displays the installed TypeScript version.

---

## 3. Create a Project Folder

```bash
mkdir ts-hello
cd ts-hello
```

* `mkdir ts-hello` → creates a new folder
* `cd ts-hello` → navigates into the folder

---


## 4. Create a TypeScript File

```bash
code main.ts
```

* Creates a new file named `main.ts` and opens it in VS Code.

---

## 5. Write Some Code

```ts
function log(message: string) {
    console.log(message);
}

let message = 'Hello World';

log(message);
```

Here, we used `string` type and `let` instead of `var` (recommended in TypeScript).

---

## 6. Transpile TypeScript to JavaScript

```bash
tsc main.ts
```

* Compiles `main.ts` into `main.js`.
* Check the folder contents:

```bash
dir
```

Now you’ll see:

```
main.ts  
main.js
```

---

## 7. Generated JavaScript File

```js
function log(message) {
    console.log(message);
}
var message = 'Hello World';
log(message);
```

* The output is plain JavaScript.
* This shows that **all JavaScript code is valid TypeScript code**.

---
