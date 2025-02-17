# React Memory Leak in useEffect with setInterval
This repository demonstrates a common React bug involving memory leaks when using `setInterval` within the `useEffect` hook without proper cleanup.  The `bug.js` file showcases the erroneous code, while `bugSolution.js` provides the corrected version.

## Problem
The initial implementation forgets to clear the interval created by `setInterval` when the component unmounts.  This leads to the interval continuing to run indefinitely, consuming resources and eventually causing memory issues.

## Solution
The solution involves using a cleanup function within the `useEffect` hook. This function, returned from the `useEffect` callback, is executed before the component unmounts, allowing for the proper clearing of the interval using `clearInterval`.