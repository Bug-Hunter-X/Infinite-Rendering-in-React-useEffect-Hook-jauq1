# Infinite Rendering Bug in React useEffect Hook

This repository demonstrates a common error in React's `useEffect` hook: infinite rendering caused by a missing dependency array.  The `useEffect` hook is called after every render, leading to an infinite loop and a crashing application.

## Bug Description
The `MyComponent` component uses the `useEffect` hook to log a message after each render.  However, the dependency array is missing, which means the effect runs after every render, triggering an infinite loop. This is because the `count` state variable constantly updates and triggers rerenders, creating a cycle.

## Solution
The solution involves adding a dependency array to the `useEffect` hook. The dependency array specifies the variables that should trigger the effect.  If any value in the array changes, then the effect will run. By adding `[count]` as the dependency array, the effect only runs when the `count` variable changes.

## How to Reproduce
1. Clone the repository.
2. Run `npm install`.
3. Run `npm start`.
4. Observe the infinite rendering in the console and the application's crash.