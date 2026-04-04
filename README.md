# CS++ JavaScript — Arrays

> **Unit 8.5** | 100 Points | 7 Automated Tests

In this assignment you will learn how to use **arrays** — ordered lists that store multiple values in a single variable. You will collect numbers from the user and calculate statistics.

---

## Table of Contents

1. [What Is an Array?](#what-is-an-array)
2. [Creating Arrays](#creating-arrays)
3. [Accessing Elements](#accessing-elements)
4. [Adding Elements with .push()](#adding-elements-with-push)
5. [Looping Through Arrays](#looping-through-arrays)
6. [Common Array Patterns](#common-array-patterns)
7. [Assignment](#assignment)
8. [Scoring Rubric](#scoring-rubric)
9. [Tips for Success](#tips-for-success)
10. [FAQ](#faq)

---

## What Is an Array?

An **array** is a list of values stored in a single variable:

```javascript
const colors = ["red", "green", "blue"];
const scores = [95, 87, 72, 100];
```

Without arrays, you would need a separate variable for each value — impractical for large collections.

> **Why `const` for arrays?** Use `const` when the variable itself won't be reassigned to a different array. You can still change the *contents* of a `const` array — `.push()`, indexing, and other modifications all work. What `const` prevents is pointing the variable at a completely new array. This is a best practice because it makes your code clearer: readers know the variable always refers to the same array.

---

## Creating Arrays

Create an empty array and add items later:

```javascript
const numbers = [];  // empty array — const is fine, we'll .push() into it
```

Or create an array with values:

```javascript
const fruits = ["apple", "banana", "cherry"];
```

---

## Accessing Elements

Array elements are numbered starting at **0** (called the **index**):

```javascript
const colors = ["red", "green", "blue"];
// Index:       0       1        2

let first = colors[0];   // "red"
let second = colors[1];  // "green"
let last = colors[2];    // "blue"
```

Use `.length` to get the number of elements:

```javascript
colors.length  // 3
```

---

## Adding Elements with .push()

`.push()` adds a value to the **end** of an array:

```javascript
const numbers = [];
numbers.push(10);   // [10]
numbers.push(20);   // [10, 20]
numbers.push(30);   // [10, 20, 30]
```

> Notice we declared `numbers` with `const` but we can still `.push()` into it. That's because `const` only prevents *reassignment* (`numbers = [1, 2, 3]` would fail), not *mutation* (changing the contents).

---

## Looping Through Arrays

Use a `for` loop to visit every element:

```javascript
const scores = [95, 87, 72];
for (let i = 0; i < scores.length; i++) {
  console.log(scores[i]);
}
// Prints: 95, 87, 72 (one per line)
```

The loop variable `i` goes from `0` to `length - 1`, which covers every valid index.

---

## Common Array Patterns

### Building a String from an Array

```javascript
let result = "";
for (let i = 0; i < arr.length; i++) {
  result = result + arr[i];
  if (i < arr.length - 1) {
    result = result + ", ";
  }
}
```

### Calculating a Sum

```javascript
let sum = 0;
for (let i = 0; i < arr.length; i++) {
  sum = sum + arr[i];
}
```

### Finding the Largest Value

```javascript
let largest = arr[0];
for (let i = 1; i < arr.length; i++) {
  if (arr[i] > largest) {
    largest = arr[i];
  }
}
```

### Counting Items that Match a Condition

```javascript
let count = 0;
for (let i = 0; i < arr.length; i++) {
  if (arr[i] % 2 === 0) {
    count = count + 1;
  }
}
```

---

## Assignment

This program uses `prompt()` for input and `console.log()` for output. It runs automatically when the page loads. Open the browser console (F12) to see results.

### Warm-Up: Favorite Colors — 15 points

1. Create an array with exactly three strings: `"red"`, `"green"`, `"blue"`
2. Use a `for` loop to print each one:
   - `Color: red`
   - `Color: green`
   - `Color: blue`

### Number Analyzer — 70 points

1. Create an empty array
2. Use a `for` loop to prompt for 5 numbers and `.push()` each into the array
3. Print the numbers on one line: `Numbers: 10, 20, 30, 40, 50`
4. Calculate and print the sum: `Sum: 150`
5. Calculate and print the average: `Average: 30`
6. Count and print even numbers: `Even count: 5`
7. Find and print the largest: `Largest: 50`

### Code Quality — 15 points

- **Uses an array** — brackets `[]` or `.push()` (10 points)
- **Uses a for loop** — `for (` (5 points)

---

## Scoring Rubric

| # | Test | Points | What the autograder checks |
|---|------|--------|---------------------------|
| 1 | Colors warm-up | 15 | Prints "Color: red", "Color: green", "Color: blue" |
| 2 | Uses an array | 10 | Source contains `[]` or `.push(` |
| 3 | Uses a for loop | 5 | Source contains `for (` |
| 4 | Numbers list | 15 | Prints "Numbers: 10, 20, 30, 40, 50" |
| 5 | Sum | 15 | Prints "Sum: 150" |
| 6 | Average and even count | 20 | Prints "Average: 30" and "Even count: 5" |
| 7 | Largest | 20 | Prints "Largest: 50" |
| | **Total** | **100** | |

---

## Tips for Success

1. **Start with the colors warm-up** — it teaches array basics before the harder part
2. **Use `parseFloat()` when collecting numbers** — prompt returns strings
3. **Build the number list string carefully** — add ", " between numbers but not after the last one
4. **Test with known values** — if you enter 10, 20, 30, 40, 50 you should get Sum: 150, Average: 30
5. **Even check**: a number is even if `number % 2 === 0`
6. **Open the console** — all output goes to `console.log()`, not `alert()`

---

## FAQ

**Q: Why console.log() instead of alert()?**
When a program has many outputs, using `alert()` for each one would be annoying (too many popups). `console.log()` prints to the developer console, which is better for multiple outputs.

**Q: How do I open the browser console?**
Press F12, or right-click the page and choose "Inspect", then click the "Console" tab.

**Q: What does `.push()` do?**
It adds a value to the end of an array. `numbers.push(42)` adds `42` to the end of the `numbers` array.

**Q: Why start the largest with `arr[0]` instead of 0?**
If all numbers are negative, starting with 0 would give a wrong answer. Starting with the first actual value guarantees correctness.

---

View all assignments at [csplusplus.com/js-tests](https://csplusplus.com/js-tests)

*CS++ — AP Computer Science Principles — [csplusplus.com](https://csplusplus.com)*
