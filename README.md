# React useEffect Performance Issue

This repository demonstrates a common performance issue in React applications related to the `useEffect` hook. The `useEffect` hook is used without dependencies, causing unnecessary re-renders and impacting performance. 

## Problem

The `MyComponent` component uses `useEffect` to log a message to the console on every render.  This is inefficient because the effect doesn't depend on any state or props.  The effect runs every time the component re-renders, even if the logged message is not relevant to the component's update. This will slow down your application with more complex and heavier tasks inside useEffect. 

## Solution

The solution is to provide an empty dependency array `[]` to the `useEffect` hook. This ensures that the effect runs only once after the initial render.  If the effect needs to update based on state or props, you should include those values in the dependency array.