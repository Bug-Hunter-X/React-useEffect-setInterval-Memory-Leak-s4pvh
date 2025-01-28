# React useEffect setInterval Memory Leak

This repository demonstrates a common mistake when using the `setInterval` function within the `useEffect` hook in React.  Failing to properly clean up the interval leads to a memory leak and unexpected behavior.

The `bug.js` file shows the problematic code, and `bugSolution.js` provides the corrected version.

## Bug Description

The component uses `setInterval` to update a counter every second.  However, it fails to clear the interval using `clearInterval` when the component unmounts. This results in the interval continuing to run, even after the component is no longer rendered, leading to unnecessary updates and potential memory leaks.

## Solution

The solution involves adding a cleanup function to the `useEffect` hook to clear the interval before the component unmounts.  This ensures that no resources are wasted.