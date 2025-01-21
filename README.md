# React useEffect Infinite Loop Bug

This repository demonstrates a common bug in React's `useEffect` hook: an infinite loop caused by an incorrectly defined dependency array.

## Bug Description
The `useEffect` hook is used to perform side effects, such as data fetching or DOM manipulations.  However, if the dependency array is missing or incorrect, the effect might run repeatedly, leading to an infinite loop and potentially crashing the application.

In this example, the `useEffect` hook logs the current count.  The problem is that the `count` variable is not included in the dependency array; therefore, this effect will run on every render, changing the count, which triggers a re-render, and the cycle repeats. The solution is to include `count` in the dependency array.