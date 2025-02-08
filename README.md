# JavaScript Closure Issue in setTimeout Loop

This repository demonstrates a common JavaScript closure issue that arises when using loops with `setTimeout` or `setInterval`.  The problem stems from how variables are captured within closures.

## Bug Description
The `bug.js` file contains a function that uses a `for` loop to schedule multiple calls to `console.log` using `setTimeout`.  You might expect it to log numbers from 0 to 9, but it logs 10 ten times.  This is because closures in JavaScript capture the variable's reference, not its value at the time of the closure creation.

## Solution
The `bugSolution.js` file demonstrates a solution using an immediately invoked function expression (IIFE) to create a new scope for each iteration of the loop. This ensures each callback has its own copy of the `i` value at the time the callback is created.