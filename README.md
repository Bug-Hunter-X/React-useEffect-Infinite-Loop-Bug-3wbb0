# React useEffect Infinite Loop Bug

This repository demonstrates a common error in React's `useEffect` hook: an infinite loop caused by an incorrect dependency array.

## Bug Description
The `MyComponent` uses `useEffect` to log the current `count` to the console. However, the dependency array `[count]` is not correctly defined.

Because the `setCount` function is called inside the effect which modifies `count` the component renders infinitely causing a loop. 

## How to Reproduce
1. Clone this repository.
2. Run `npm install` to install dependencies.
3. Run `npm start` to start the development server.
4. Observe the infinite loop in the console and the browser crashing.

## Solution
The solution involves correctly specifying the dependency array.  If you don't need the effect to run on every render, then remove `count` from the dependency array.