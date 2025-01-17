# React setInterval Memory Leak
This repository demonstrates a common error in React applications involving the use of `setInterval` within the `useEffect` hook without proper cleanup.  The incorrect implementation leads to a memory leak as the interval continues to run indefinitely even after the component unmounts.

The `bug.js` file showcases the flawed implementation. The `bugSolution.js` file provides the correct solution.

## How to reproduce the bug
1. Clone this repository.
2. Run `npm install` to install dependencies.
3. Run `npm start` to start the development server.
4. Observe the continuously incrementing counter, even after the component is unmounted (try navigating away from the page and then back).

## Solution
The solution involves returning a cleanup function from the `useEffect` hook which clears the interval when the component unmounts or the dependency array changes.