# React setInterval Memory Leak

This example demonstrates a common mistake in React components: using `setInterval` within `useEffect` without proper cleanup. This leads to memory leaks because the interval continues running even after the component unmounts.

## Bug
The `bug.js` file contains a React component that increments a counter every second using `setInterval`.  The problem is the missing cleanup function in the `useEffect` hook.  This means the interval keeps running indefinitely, even when the component is no longer displayed, resulting in a memory leak.

## Solution
The `bugSolution.js` file corrects this by using the return value of `useEffect` to implement a cleanup function. This function clears the interval when the component unmounts, preventing the memory leak.

## How to reproduce the bug
1. Clone this repository.
2. Run `npm install` to install dependencies.
3. Run `npm start` to start the development server.
4. Observe the counter incrementing every second.
5. Unmount the component (e.g., by navigating away from the page). The interval will still run in the background.

## How to fix the bug
1. Replace `bug.js` with `bugSolution.js`.
2. Run `npm start` again.
3. Observe that the counter stops incrementing when the component unmounts.