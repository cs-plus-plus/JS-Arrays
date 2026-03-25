# CS++ JavaScript — Lesson 8.5: Arrays

> **Lesson 8.5** | 100 Points | 6 Autograded Tests

In this assignment you will use `prompt()` and `console.log()` to build a traffic light program and collect numbers into an array for calculations. No DOM manipulation — everything uses prompt for input and console.log for output.

---

## Table of Contents

1. [Concepts You Need](#concepts-you-need)
2. [Project Overview](#project-overview)
3. [Exact Requirements](#exact-requirements)
4. [File Structure](#file-structure)
5. [Autograding](#autograding)
6. [Try It Yourself — Practice Examples](#try-it-yourself--practice-examples)
7. [Tips for Success](#tips-for-success)
8. [FAQ](#faq)

---

## Concepts You Need

### Arrays

An array is an ordered list of values:

```javascript
let colors = ["red", "green", "blue"];
console.log(colors[0]);        // "red" (first element, index 0)
console.log(colors.length);    // 3

colors.push("yellow");         // add to the end
console.log(colors);           // ["red", "green", "blue", "yellow"]
```

### Accessing Array Elements

```javascript
let nums = [10, 20, 30];

// Read by index
console.log(nums[0]);   // 10
console.log(nums[2]);   // 30

// Change by index
nums[1] = 25;
console.log(nums);      // [10, 25, 30]

// Loop through all elements
for (let i = 0; i < nums.length; i++) {
    console.log(nums[i]);
}
```

### Useful Array Methods

| Method | What It Does | Example |
|--------|-------------|---------|
| `push(value)` | Add to the end | `arr.push(42)` |
| `pop()` | Remove from the end | `arr.pop()` |
| `length` | Number of elements | `arr.length` |
| `indexOf(value)` | Find position of a value | `arr.indexOf("red")` |

### String Comparison (Case-Insensitive)

Use `.toLowerCase()` to compare strings regardless of case:

```javascript
let input = "RED";
if (input.toLowerCase() === "red") {
    console.log("It's red!");  // this runs
}
```

### The Modulo Operator (%)

The remainder operator tells you if a number is even or odd:

```javascript
10 % 2   // 0 (even — no remainder)
7 % 2    // 1 (odd — remainder of 1)

if (num % 2 === 0) {
    console.log("Even");
} else {
    console.log("Odd");
}
```

### Calculating an Average

```javascript
let nums = [10, 20, 30, 40, 50];
let sum = 0;

for (let i = 0; i < nums.length; i++) {
    sum += nums[i];
}

let average = sum / nums.length;
console.log("Average: " + average);  // Average: 30
```

---

## Project Overview

Your `script.js` runs two tasks in order when the page loads:

1. **Traffic Light** — Ask for a color, print the matching action 5 times
2. **Number Collection** — Ask for 5 numbers, store them in an array, calculate the average and count even numbers

---

## Exact Requirements

### Part 1: Traffic Light

1. Call `prompt()` once to ask for a traffic light color
2. The input should be **case-insensitive** (accept "RED", "red", "Red", etc.)
3. If the color is valid, print the matching action **exactly 5 times** using `console.log()`:

| Color | Output (printed 5 times) |
|-------|-------------------------|
| green | `Action: Go` |
| yellow | `Action: Slow` |
| red | `Action: Stop` |

4. If the color is not red, yellow, or green, print exactly: `Invalid color` (once, no action lines)

### Part 2: Number Collection

1. Call `prompt()` **five separate times** to collect five numbers
2. Store all five numbers in an **array**
3. Calculate and print the average with the exact format: `Average: <number>`
4. Count how many of the five numbers are even and print with the exact format: `Even count: <number>`

### Full Example Output (green, numbers 2, 4, 6, 8, 10)

```
Action: Go
Action: Go
Action: Go
Action: Go
Action: Go
Average: 6
Even count: 5
```

### Example with Invalid Color (blue, numbers 1, 2, 3, 4, 5)

```
Invalid color
Average: 3
Even count: 2
```

---

## File Structure

```
JS-Arrays/
├── index.html              <-- Loads script.js (provided)
├── script.js               <-- YOUR CODE GOES HERE
└── .github/
    └── workflows/
        └── classroom.yml   <-- Autograding tests (DO NOT MODIFY)
```

**Edit only `script.js`.** Write all your code at the top level so it runs when the file loads.

---

## Autograding

| Test | What It Checks | Points |
|------|---------------|--------|
| Green action lines | Prints "Action: Go" five times | 15 |
| Yellow action lines | Prints "Action: Slow" five times | 15 |
| Red action lines | Prints "Action: Stop" five times | 15 |
| Invalid color message | Prints "Invalid color", no action lines | 10 |
| Average and even count | Correct "Average:" and "Even count:" output | 30 |
| Uses array for numbers | Static analysis: finds brackets, push/index usage | 15 |

**Total: 100 points**

---

## Try It Yourself — Practice Examples

Create `practice.js` and run it with `node practice.js`.

**Example 1 — Array basics:**
```javascript
// practice.js — building an array
let numbers = [];
numbers.push(10);
numbers.push(20);
numbers.push(30);
console.log("Array:", numbers);        // Array: [10, 20, 30]
console.log("Length:", numbers.length); // Length: 3
console.log("First:", numbers[0]);     // First: 10
console.log("Last:", numbers[numbers.length - 1]); // Last: 30
```

**Example 2 — Sum and average:**
```javascript
// practice.js — calculating average
let nums = [10, 20, 30, 40, 50];
let sum = 0;
for (let i = 0; i < nums.length; i++) {
    sum += nums[i];
}
console.log("Average: " + (sum / nums.length));
// Output: Average: 30
```

**Example 3 — Counting even numbers:**
```javascript
// practice.js — counting evens
let nums = [1, 2, 3, 4, 5];
let evenCount = 0;
for (let i = 0; i < nums.length; i++) {
    if (nums[i] % 2 === 0) {
        evenCount++;
    }
}
console.log("Even count: " + evenCount);
// Output: Even count: 2
```

**Example 4 — Case-insensitive comparison:**
```javascript
// practice.js — case insensitive
let colors = ["RED", "Green", "YELLOW", "blue"];
for (let color of colors) {
    let lower = color.toLowerCase();
    if (lower === "red" || lower === "yellow" || lower === "green") {
        console.log(color + " is a valid traffic light color");
    } else {
        console.log(color + " is invalid");
    }
}
```

---

## Tips for Success

1. Use `parseFloat()` or `parseInt()` to convert prompt input to numbers before doing math
2. Use `.toLowerCase()` on the color input to handle any capitalization
3. You must use an **array** to store the five numbers — the test checks for this using static analysis
4. Print each action line separately with `console.log()`, not all on one line
5. The average should be a regular number (not formatted to a specific number of decimals)
6. Test your code with different colors and number combinations

---

## FAQ

**Q: Does the color comparison need to be case-insensitive?**
Yes. The user might type "RED", "Red", or "red" — all should work. Use `.toLowerCase()` on the input.

**Q: What if the user types a number with decimals for the number collection?**
Use `parseFloat()` to handle both integers and decimals. The even count check should use the modulo operator (`% 2 === 0`).

**Q: How does the test know I used an array?**
The test performs static analysis on your `script.js` file, looking for array syntax like `[]`, `.push()`, or bracket access like `arr[i]`.

**Q: Should I use console.log or alert for output?**
Use `console.log()` for all output in this assignment. Do not use `alert()`.

---

View all assignments and scoring breakdowns at [csplusplus.com/js-tests](https://csplusplus.com/js-tests)

*CS++ — AP Computer Science Principles — [csplusplus.com](https://csplusplus.com)*
