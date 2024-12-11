# React useEffect Hook Memory Leak

This example demonstrates a common mistake in React's `useEffect` hook: forgetting to include a cleanup function to prevent memory leaks.  The `setInterval` function, if not cleared when the component unmounts, will continue to run in the background, leading to unnecessary resource consumption.

## Bug
The `bug.js` file shows the component with the memory leak.  The `setInterval` function is started in the `useEffect` hook, but there's no way to stop it when the component is unmounted.

## Solution
The `bugSolution.js` file corrects this by returning a cleanup function from the `useEffect` hook. This function will clear the interval when the component is unmounted or the dependency array changes.