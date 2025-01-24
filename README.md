# Unexpected State Updates in React's useEffect Hook

This repository demonstrates a subtle bug related to consecutive state updates within a `useEffect` hook in React.  The issue arises from the asynchronous nature of state updates, where multiple updates within a single render cycle might not produce the expected result.

## Bug Description

The `bug.js` file contains a component that increments a counter using `setCount`.  Two `setCount` calls are made in quick succession.  Due to the asynchronous updates, the second `setCount` call might not reflect the change made by the first, resulting in an incorrect final count.

## Solution

The `bugSolution.js` file provides a corrected implementation. It uses functional updates passed to `setCount` to ensure the second update takes into account the first update.