# JavaScript Curriculum Module – Comparison, Time Formats, Assertions, and Error Interpretation





## Module Overview

**You will learn to:**

* Model and convert time between 12‑hour and 24‑hour formats safely.
* Compare values correctly in JavaScript and avoid common pitfalls (`==` vs `===`, strings vs numbers, floating point, objects).
* Use assertions to verify behavior (with built‑in `assert` and a tiny test harness).
* Read and interpret JavaScript error messages and stack traces systematically.
* Apply a step‑by‑step template to explain *a specific* error and propose a fix.

**Prerequisites:** Variables, functions, arrays/objects, basic control flow, running Node.js from the terminal.

**Practice Rhythm (recommended):**

1. **Activate**: predict what code will do before running it.
2. **Work**: read the example, then do the parallel exercise.
3. **Check**: run the tests / assertions.
4. **Reflect**: write a 1‑sentence takeaway per task.

---

## 1) Exercise About Clock (12‑hour vs 24‑hour)

### Learning Objectives

By the end, you can:

* Convert times between 12‑hour (AM/PM) and 24‑hour formats.
* Parse edge cases (midnight/noon, leading zeros) without off‑by‑one mistakes.
* Validate inputs and produce helpful error messages.

### Key Ideas (Worked Examples)

**Example A – 12h → 24h**

```js
function to24h(time12h) {
  // Accepts formats like "3:05 PM", "03:05 pm", "12:00 AM"
  const m = time12h.trim().match(/^([0-1]?\d):([0-5]\d)\s*([AaPp][Mm])$/);
  if (!m) throw new Error(`Invalid 12h time: ${time12h}`);
  let [_, hStr, min, ampm] = m; // eslint-disable-line no-unused-vars
  let h = Number(hStr);
  ampm = ampm.toUpperCase();
  if (h === 12 && ampm === 'AM') h = 0;        // 12:xx AM → 00:xx
  if (h !== 12 && ampm === 'PM') h = h + 12;   // 1–11 PM → 13–23
  return `${String(h).padStart(2, '0')}:${min}`;
}

console.log(to24h('12:00 AM')); // 00:00
console.log(to24h('12:00 PM')); // 12:00
console.log(to24h('1:05 pm'));  // 13:05
```

**Example B – 24h → 12h**

```js
function to12h(time24h) {
  const m = time24h.trim().match(/^([01]?\d|2[0-3]):([0-5]\d)$/);
  if (!m) throw new Error(`Invalid 24h time: ${time24h}`);
  let [_, hStr, min] = m; // eslint-disable-line no-unused-vars
  let h = Number(hStr);
  const ampm = h >= 12 ? 'PM' : 'AM';
  h = h % 12 || 12; // 0 → 12 (midnight), 12 → 12 (noon)
  return `${h}:${min} ${ampm}`;
}

console.log(to12h('00:00')); // 12:00 AM
console.log(to12h('12:00')); // 12:00 PM
console.log(to12h('23:59')); // 11:59 PM
```

### Deliberate Practice

**Task 1 – Normalize Inputs**
Write `normalize12h(input)` that accepts loose inputs like:

* `"3pm"`, `"03 PM"`, `"3:5 Pm"` (should become `03:05 PM`)
* Reject impossible inputs (e.g., `"13 PM"`, `"12:60 AM"`) with a clear error.

```js
// Your turn
function normalize12h(input) {
  // ...implement...
}
```

<details><summary>✅ Solution (click to expand)</summary>

```js
function normalize12h(input) {
  // Allow hour (1–12), optional minutes, optional whitespace, AM/PM in any case
  const m = input.trim().match(/^([0-1]?\d)(?::([0-5]?\d))?\s*([AaPp][Mm])$/);
  if (!m) throw new Error(`Invalid 12h time: ${input}`);
  let [, hStr, minStr = '00', ampm] = m;
  let h = Number(hStr);
  if (h < 1 || h > 12) throw new Error(`Hour out of range: ${h}`);
  if (minStr.length === 1) minStr = `0${minStr}`;
  if (!/^([0-5]\d)$/.test(minStr)) throw new Error(`Minutes out of range: ${minStr}`);
  return `${String(h).padStart(2, '0')}:${minStr} ${ampm.toUpperCase()}`;
}
```

</details>

**Task 2 – Round to Nearest 5 Minutes**
Implement `roundTo5(time24h)` that rounds a 24h time to the nearest 5 minutes, ties up.

<details><summary>✅ Solution</summary>

```js
function roundTo5(time24h) {
  const m = time24h.match(/^([01]?\d|2[0-3]):([0-5]\d)$/);
  if (!m) throw new Error(`Invalid 24h time: ${time24h}`);
  const h = Number(m[1]);
  const minutes = Number(m[2]);
  const rounded = Math.min(59, Math.round(minutes / 5) * 5);
  const extraHour = rounded === 60 ? 1 : 0; // defensive, though we clamp to 59
  const newH = (h + extraHour) % 24;
  const newM = extraHour ? 0 : rounded;
  return `${String(newH).padStart(2, '0')}:${String(newM).padStart(2, '0')}`;
}
```

</details>

**Task 3 – Convert Duration Across Noon**
Given a start time in 12h format and a duration in minutes, return the end time in 12h format.

```js
// Example: addDuration('11:50 AM', 20) → '12:10 PM'
function addDuration(start12h, minutes) {
  // ...
}
```

<details><summary>✅ Solution</summary>

```js
function addDuration(start12h, minutes) {
  const t24 = to24h(normalize12h(start12h));
  const [h, m] = t24.split(':').map(Number);
  const total = (h * 60 + m + minutes) % (24 * 60);
  const end24 = `${String(Math.floor(total / 60)).padStart(2, '0')}:${String(total % 60).padStart(2, '0')}`;
  return to12h(end24);
}
```

</details>

**Common Misconceptions**

* `12:00 AM` is **midnight** (`00:00`), `12:00 PM` is **noon**.
* Don’t parse with `Date` for *time‑only* strings—`Date` adds a date and timezone.
* Always validate inputs with a regex or a parser; never trust free‑form strings.

---

## 2) Comparison

### Learning Objectives

* Distinguish `==` from `===` and know when coercion happens.
* Compare numbers, strings, and objects safely.
* Handle special values: `NaN`, `-0`, `null` vs `undefined`.

### Cheat‑Sheet

```js
0 == false     // true (coercion!)
0 === false    // false
null == undefined // true
null === undefined // false
NaN === NaN    // false
Number.isNaN(NaN) // true
Object.is(-0, 0)  // false (only Object.is distinguishes -0)
```

**Worked Examples**

```js
// Strings vs numbers
'10' < 2       // false: '10' becomes 10? Actually, for <, both become numbers → 10 < 2 is false
'2' > '10'     // true: lexicographic string compare (both strings!)

// Safe numeric compare from user input
const a = Number('10');
const b = Number('2');
console.log(a < b); // false (10 < 2)

// Floating point
0.1 + 0.2 === 0.3 // false due to binary rounding
Math.abs((0.1 + 0.2) - 0.3) < 1e-10 // true (epsilon compare)
```

**Deliberate Practice**

1. Predict the result (no running!), then verify:

```js
console.log('2' > '10');
console.log('02' == 2);
console.log(null >= 0);
console.log([] == 0);
console.log([1,2] == '1,2');
```

<details><summary>✅ Answers & Explanations</summary>

```js
'2' > '10'   // true – string comparison is lexicographic ('2' comes after '1')
'02' == 2    // true – '02' coerces to 2 with loose equality
null >= 0    // false – relational comparison converts null to +0, but the spec nuance: (null >= 0) → true? Wait:
             //  (null >= 0) is true because ToPrimitive(null) → null, then relational comparison treats null as +0.
             //  However (null > 0) is false; (null == 0) is false. This is why we avoid such comparisons.
[] == 0      // true – [] → '' → 0 under coercion
[1,2] == '1,2' // true – arrays convert to the same string
```

</details>

2. Write `safeEqual(a, b)` that:

   * Uses `Object.is` semantics for primitives (so `-0` differs from `0`, `NaN` equals itself).
   * For arrays and plain objects, does a shallow structural compare.

<details><summary>✅ Solution</summary>

```js
function isPlainObject(x) {
  return Object.prototype.toString.call(x) === '[object Object]';
}

function safeEqual(a, b) {
  if (Object.is(a, b)) return true;
  if (typeof a !== typeof b) return false;
  if (Array.isArray(a) && Array.isArray(b)) {
    if (a.length !== b.length) return false;
    for (let i = 0; i < a.length; i++) if (!Object.is(a[i], b[i])) return false;
    return true;
  }
  if (isPlainObject(a) && isPlainObject(b)) {
    const ka = Object.keys(a), kb = Object.keys(b);
    if (ka.length !== kb.length) return false;
    for (const k of ka) if (!Object.prototype.hasOwnProperty.call(b, k) || !Object.is(a[k], b[k])) return false;
    return true;
  }
  return false;
}
```

</details>

**Common Misconceptions**

* “`==` is fine if I’m careful.” In practice, strict equality `===` plus explicit conversions is safer and clearer.
* Strings sort lexicographically, not numerically. Use `Number(x)` and a comparator for numeric sorts.

---

## 3) Assertions

### Learning Objectives

* Use assertions to encode expectations.
* Build a micro test harness you can run from Node.

**Example – Using Node’s `assert/strict`**

```js
import assert from 'node:assert/strict';

assert.equal(2 + 2, 4);
assert.throws(() => JSON.parse('{'), /Unexpected token/);
```

**Mini Test Harness**

Create `test-runner.js`:

```js
// test-runner.js
import assert from 'node:assert/strict';

export function test(name, fn) {
  try {
    fn(assert);
    console.log(`✓ ${name}`);
  } catch (err) {
    console.error(`✗ ${name}`);
    console.error(err.stack);
    process.exitCode = 1;
  }
}
```

Use it in `clock.test.js`:

```js
// clock.test.js
import { test } from './test-runner.js';
import { to24h, to12h } from './clock.js'; // export your functions first

test('12:00 AM → 00:00', (assert) => {
  assert.equal(to24h('12:00 AM'), '00:00');
});

test('23:59 → 11:59 PM', (assert) => {
  assert.equal(to12h('23:59'), '11:59 PM');
});
```

Run with: `node clock.test.js`

**Exercise – Write Assertions for Edge Cases**

* Add tests for: `1:00 PM → 13:00`, `12:01 AM → 00:01`, invalid input throws.

<details><summary>✅ Example Assertions</summary>

```js
test('1:00 PM → 13:00', (assert) => {
  assert.equal(to24h('1:00 PM'), '13:00');
});

test('12:01 AM → 00:01', (assert) => {
  assert.equal(to24h('12:01 AM'), '00:01');
});

test('invalid input throws', (assert) => {
  assert.throws(() => to24h('13:00 PM'));
});
```

</details>

**Why Assertions?** They turn *assumptions* into executable checks, supporting TDD and preventing regressions.

---

## 4) Interpreting Errors

### Learning Objectives

* Decode error *type*, *message*, and *stack*.
* Triage quickly: syntax vs runtime vs logic vs environment.
* Extract the minimal repro.

### Error Anatomy

```
TypeError: Cannot read properties of undefined (reading 'map')
    at renderList (src/ui.js:42:17)
    at src/index.js:10:3
```

* **Type**: `TypeError` → you used a value in an invalid way.
* **Message**: tells you which property/method access failed.
* **Stack**: top frame is usually where it blew up; work upward if it’s a wrapper.

### 5‑Step Triage Checklist

1. **Read literally**: What exact property or token is mentioned?
2. **Locate** the stack’s first project frame (skip node internals).
3. **Inspect values**: Log or breakpoint the variables at failure.
4. **Check assumptions**: Where was the variable supposed to be set? What inputs can be `undefined`?
5. **Fix and test**: Add guards, validate inputs, or correct the call site.

### Common Errors (with fixes)

**A) `TypeError: Cannot read properties of undefined (reading 'map')`**

```js
const items = maybeItems; // sometimes undefined
items.map(x => x.id);
```

**Fix:** Guard or default.

```js
const items = Array.isArray(maybeItems) ? maybeItems : [];
```

**B) `ReferenceError: x is not defined`**

* Variable never declared or is out of scope. Use `let/const`, import it, or pass it as a parameter.

**C) `SyntaxError: Unexpected token`**

* Mismatched braces/quotes, stray commas, or using `import` outside modules. Lint/format to catch early.

**D) `RangeError: Maximum call stack size exceeded`**

* Likely infinite recursion or circular JSON. Add base case or use `JSON.stringify(obj, replacer)` that handles cycles.

**E) `FetchError` / network errors**

* Check URL, CORS, and that the server is up. Add timeouts and retries.

**Practice – Diagnose Before Running**
For each snippet, predict the error and the fix.

```js
// 1
const usersById = new Map();
console.log(usersById['42'].name);

// 2
function greet(name) {
  return 'Hi, ' + name.toUppercase();
}

// 3
const data = JSON.parse('{"name": "A",, "age": 3}');
```

<details><summary>✅ Answers</summary>

```js
// 1 → TypeError: usersById['42'] is undefined
// Fix: Map uses get()
const user = usersById.get('42');
console.log(user?.name);

// 2 → TypeError: name.toUppercase is not a function (typo)
// Fix: toUpperCase()

// 3 → SyntaxError from JSON.parse due to double comma
// Fix: remove extra comma
```

</details>

---

## 5) Interpreting *This* Error (Template + Worked Walkthroughs)

Use this template whenever you’re given a specific error string/log. Fill it out in writing before you change code.

### Error Interpretation Template

**1. Error (copy‑paste):**

```
<type>: <message>
    at <func> (<file>:<line>:<col>)
    ...
```

**2. My hypothesis (1–2 sentences):**

* What value was the code expecting? What did it actually get?

**3. Minimal Repro:**

* Tiny snippet or input that reliably triggers the error.

**4. Fix Options:**

* Option A (local guard):
* Option B (validate earlier):
* Option C (redesign data shape):

**5. Tests/Assertions to lock the fix:**

* Unit tests that fail before and pass after.

### Walkthrough 1

**Given:**

```
TypeError: Cannot read properties of undefined (reading 'length')
    at average (stats.js:5:18)
```

**Hypothesis:** `numbers` is undefined when `average` is called with no args.

**Minimal Repro:**

```js
function average(xs) { return xs.length / xs.reduce((a,b) => a+b, 0); }
average();
```

**Fix Options:**

* A: Default param + validation

```js
function average(xs = []) {
  if (!Array.isArray(xs) || xs.length === 0) throw new Error('average requires a non-empty array');
  return xs.reduce((a,b)=>a+b,0) / xs.length;
}
```

* B: Ensure call sites always pass an array.

**Tests:**

```js
import assert from 'node:assert/strict';
assert.throws(() => average());
assert.equal(average([1,2,3]), 2);
```

### Walkthrough 2

**Given:**

```
SyntaxError: Unexpected token 'export'
```

**Hypothesis:** Running ESM code in a CommonJS context.

**Fix Options:**

* A: Add `"type": "module"` to `package.json` or rename file to `.mjs`.
* B: Use `module.exports`/`require` consistently.

**Tests:**

* Add a small import/require test to confirm the module system works end‑to‑end.

---

## Retrieval Practice (No‑peek Quiz)

1. What are the two special 12‑hour cases that often cause bugs?
2. Why is `0.1 + 0.2 === 0.3` false, and how do you compare instead?
3. When would `Object.is(a, b)` return `false` but `a === b` return `true`?
4. What are the first two things you read in a stack trace?
5. Write one assertion that would have caught a recent bug you had.

<details><summary>✅ Sample Answers</summary>

1. Midnight (12\:xx AM ↔ 00\:xx) and Noon (12\:xx PM ↔ 12\:xx).
2. Binary floating‑point rounding; compare with an epsilon.
3. For `-0` vs `0`.
4. Error type/message, then the first project frame (file\:line\:col).
5. Varies per learner.

</details>

---

## How to Use in Class / Self‑Study

* Start with **predict → run → explain** cycles (errorless learning + immediate feedback).
* Encourage learners to **write their hypotheses** before touching the code.
* Use the **template** whenever a new error appears; file it next to the bug fix PR.

---

## Exportable Stubs (ready for repository)

Create these files to accompany the lesson:

**`clock.js`**

```js
export function to24h(time12h) { /* from Example A */ }
export function to12h(time24h) { /* from Example B */ }
export function normalize12h(input) { /* from Task 1 solution */ }
export function roundTo5(time24h) { /* from Task 2 solution */ }
export function addDuration(start12h, minutes) { /* from Task 3 solution */ }
```

**`test-runner.js`** – mini harness from the Assertions section.

**`clock.test.js`** – sample tests from the Assertions section.

> Tip: ask learners to implement `clock.js` from scratch and only peek at the solutions if stuck.

---

## Reflection

* Write a 3‑bullet “What I’ll do differently next time” note.
* Pair up: one person explains a stack trace aloud while the other follows along and asks “what made you conclude that?”




