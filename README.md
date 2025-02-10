## React useEffect setInterval Memory Leak

This example demonstrates a common mistake in React: using `setInterval` within a `useEffect` hook without proper cleanup. This can lead to memory leaks and unexpected behavior.

The `bug.js` file contains the buggy code.  The `bugSolution.js` file provides the corrected implementation.

**Problem:** The `setInterval` function is called repeatedly without a way to stop it when the component unmounts. This means the interval continues to run even after the component is no longer in the DOM, causing unnecessary updates and memory consumption.

**Solution:** The corrected version uses the return value of `useEffect` to implement cleanup. The `clearInterval` function is called to stop the interval before the component unmounts, resolving the memory leak issue.