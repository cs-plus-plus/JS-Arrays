# Unit 8.5 – Arrays

## Notes
- Arrays can hold **mixed types** (numbers, strings, booleans, etc.).
- Read/write by index (`arr[i]`) and use `arr.length` to access/append at the end.
- Useful methods: `push`, `pop`, `shift`, `unshift`, `splice`, `sort` (string compare by default).

## What you’ll build
A single JavaScript file that uses `prompt()` to collect input and `console.log()` to print results.

### Program behavior (in order)
1. Ask once for a **traffic light color** (red, yellow, green — case-insensitive).
   - If valid, print the **matching action** five times with **exact** lines:
     - `Action: Stop` for red
     - `Action: Slow` for yellow
     - `Action: Go` for green
   - If not valid, print **exactly** `Invalid color` and **do not** print the five actions.
2. Ask for **five numbers** (five separate prompts). Store them in an **array**, then:
   - Print the average with the **exact** format `Average: <number>`.
   - Print how many numbers are even with the **exact** format `Even count: <number>`.

### Example (sample console output)
```
Action: Go
Action: Go
Action: Go
Action: Go
Action: Go
Average: 3
Even count: 2
```

## Required file
```
script.js
```

Place all of your code at the top level of `script.js` so it runs when the file loads.

## How it will be graded
The grader will simulate responses for `prompt()` and capture `console.log()` output to check:
- Correct action printed five times for valid colors.
- `Invalid color` when the color isn’t red/yellow/green.
- Correct average and even count for five prompted numbers.
- Use of an array to store the five numbers.
