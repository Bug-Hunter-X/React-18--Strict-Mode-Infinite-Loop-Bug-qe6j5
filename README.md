# React 18+ Strict Mode Infinite Loop Bug

This repository demonstrates a subtle bug that can occur in React 18 and later versions when using the `useEffect` hook within strict mode.  The bug arises from attempting to update state within `useEffect` using the previous state value, leading to an infinite loop.

## Bug Description

The bug is caused by a strict mode check in React 18+. Strict mode renders components twice during the initial mount. If the `useEffect` hook attempts to update state using the previous state value (which changes during the second render), the update triggers a re-render, leading to an infinite loop. 

## Solution

The solution is to use the functional update pattern for updating state in `useEffect` to avoid this infinite loop. This ensures that the updated state is always based on the most recent state value.