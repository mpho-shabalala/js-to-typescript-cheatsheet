# 🧠 JavaScript → TypeScript Cheatsheet for Full-Stack Devs

A quick reference for JavaScript developers moving into TypeScript—especially useful for frontend (React) and backend (Node.js) projects.

---

## 🧩 Variables & Types

| JavaScript              | TypeScript                             |
| ----------------------- | -------------------------------------- |
| `let x = 5`             | `let x: number = 5;`                   |
| `const s = "hi"`        | `const s: string = "hi";`              |
| `let n = null`          | `let n: null = null;`                  |
| `let anyVal = "hello";` | `let anyVal: any = "hello";` (unsafe)  |
| —                       | `let val: unknown;` (safer than `any`) |

---

## 📦 Data Types

| JavaScript                | TypeScript                                |
| ------------------------- | ----------------------------------------- |
| Arrays: `[1, 2, 3]`       | `let arr: number[] = [1, 2, 3];`          |
| Objects: `{a: 1, b: "x"}` | `let obj: {a: number, b: string};`        |
| Dynamic: `typeof x`       | Compile-time: `typeof x` (type inference) |

---

## 🔁 Loops

| JavaScript                 | TypeScript (same + type safety)         |
| -------------------------- | --------------------------------------- |
| `for (let i=0; i<10; i++)` | `for (let i: number = 0; i < 10; i++)`  |
| `for (const x of arr)`     | `for (const x of arr: number[])`        |
| `arr.forEach(f)`           | `arr.forEach((f: (x: number) => void))` |

---

## 🎯 Functions

| JavaScript                    | TypeScript                                             |
| ----------------------------- | ------------------------------------------------------ |
| `function add(a, b) {}`       | `function add(a: number, b: number): number {}`        |
| `const add = (a, b) => a + b` | `const add = (a: number, b: number): number => a + b;` |
| Default args: `f(x=5)`        | Same: `function f(x: number = 5) {}`                   |
| Rest args: `(...args)`        | `function f(...args: number[]): void {}`               |

---

## 🧱 Classes

| JavaScript          | TypeScript                     |
| ------------------- | ------------------------------ |
| `class User {}`     | `class User { name: string; }` |
| `constructor(name)` | `constructor(name: string) {}` |
| `this.name = name`  | `this.name: string = name;`    |
| `extends Base`      | `class User extends Base {}`   |

---

## 🧠 Conditionals

| JavaScript  | TypeScript                       |
| ----------- | -------------------------------- |
| `if (x)`    | `if (x)` (type narrowing works!) |
| `x ? a : b` | Same                             |
| `x ?? y`    | Same (nullish coalescing)        |

---

## 📚 Modules & Imports

| JavaScript             | TypeScript                    |
| ---------------------- | ----------------------------- |
| `import x from "mod";` | Same                          |
| `export const a = 1;`  | Same                          |
| JSDoc types            | Real types/interfaces instead |

---

## ⚠️ Error Handling

| JavaScript                 | TypeScript                                       |
| -------------------------- | ------------------------------------------------ |
| `try { ... } catch (e) {}` | Same, but `e` can be typed: `catch (e: unknown)` |
| `throw new Error("msg")`   | Same                                             |

---

## ⏱ Async/Await

| JavaScript             | TypeScript                               |
| ---------------------- | ---------------------------------------- |
| `async function foo()` | `async function foo(): Promise<void>`    |
| `await fetch()`        | Same                                     |
| `Promise.all()`        | Same, but typed: `Promise.all<User[]>()` |

---

## 🔬 Interfaces & Types

| JavaScript   | TypeScript                                     |                        |
| ------------ | ---------------------------------------------- | ---------------------- |
| Just objects | `interface User { id: number; name: string; }` |                        |
| —            | \`type ID = string                             | number;\` (union type) |

---

## 📐 Type Safety Examples

```ts
// Function with types
function add(a: number, b: number): number {
  return a + b;
}

// Interfaces
interface User {
  id: number;
  email: string;
  isAdmin?: boolean; // optional
}

const u: User = { id: 1, email: "test@example.com" };

// Generics
function identity<T>(value: T): T {
  return value;
}
```

---

## 🛠 Tooling Equivalents

| JavaScript Tool | TypeScript Equivalent         |
| --------------- | ----------------------------- |
| `eslint`        | `eslint + @typescript-eslint` |
| `prettier`      | Same                          |
| `jest`, `mocha` | `jest + ts-jest`              |
| `zod`, `yup`    | Same (works great with TS)    |
| Babel           | TypeScript compiler (`tsc`)   |
| `jsconfig.json` | `tsconfig.json`               |

---

## ✅ Tips for JS Developers Learning TS

* Start with **type inference**: `let x = 5;` → TS already knows `x` is a `number`.
* Use **interfaces** for objects and props, **types** for unions/aliases.
* Add types to **function parameters and return values** first.
* Avoid `any`—use `unknown` if you must.
* Think of TS as **autocompletion + error prevention**, not extra work.

---

Happy coding ⚡ TypeScript makes your JS **bulletproof** 🔒
