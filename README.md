# React Memory Leak: Unclosed setInterval in useEffect

This repository demonstrates a common mistake in React applications: using `setInterval` inside a `useEffect` hook without providing a cleanup function.  This leads to memory leaks as the interval continues to run even after the component is unmounted.

The `bug.js` file contains the problematic code, while `bugSolution.js` provides the corrected version.

## How to reproduce

1. Clone the repository.
2. Run `npm install`.
3. Run `npm start`.
4. Observe the counter incrementing every second.
5. Open the browser's developer tools and observe that the interval continues to run even after the component is unmounted.

## Solution

The solution involves using the return value of `useEffect` to implement a cleanup function that calls `clearInterval` to stop the interval.  Refer to `bugSolution.js` for the corrected code.