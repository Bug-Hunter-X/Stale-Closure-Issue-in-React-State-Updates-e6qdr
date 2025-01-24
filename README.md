# React Stale Closure Bug

This repository demonstrates a common, yet subtle, bug in React involving stale closures when updating component state. The bug arises from using the previous state value directly within the `setState` callback, which can lead to unexpected behavior and incorrect state updates.

## Bug Description

The `bug.js` file contains a React component that attempts to increment a counter. However, due to the asynchronous nature of state updates, using `count + 1` directly within `setCount` might not reflect the most up-to-date value. This can result in incorrect increments, especially when multiple updates are queued.

## Solution

The `bugSolution.js` file demonstrates the correct way to handle state updates.  Instead of relying on the previous state value directly, it leverages the functional update pattern to ensure that the component always uses the latest state value. This pattern ensures that the state update is based on the most recent value.