# Closure Issue in setTimeout Loop

This repository demonstrates a common closure-related issue in JavaScript when using `setTimeout` within a loop.  The problem arises because the `setTimeout` callback function does not capture the value of `i` at the time of its creation, but rather captures a reference to the variable `i`.  By the time the `setTimeout` callbacks finally execute, the loop has already completed, and `i` has its final value of 10.

## Bug
The `bug.js` file contains the problematic code.  Running this code will demonstrate the unexpected output.

## Solution
The `bugSolution.js` file provides a corrected version. This uses an Immediately Invoked Function Expression (IIFE) to create a new scope for each iteration of the loop, ensuring that the correct value of `i` is captured by each callback.