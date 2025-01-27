# React useEffect Cleanup Function Issue

This repository demonstrates a common issue with React's `useEffect` hook where the cleanup function is not reliably called when a component unmounts.  This can lead to memory leaks or unexpected behavior.

## Problem

The provided `bug.js` demonstrates a component with an `useEffect` hook. The cleanup function (within the returned function from `useEffect`) should ideally run when the component is unmounted. However, under certain circumstances, especially when the component unmounts quickly or there are other concurrent updates, the cleanup function may be skipped.

## Solution

The `bugSolution.js` file demonstrates a solution to this issue which involves using a flag to track the component's mounted state. This helps to ensure that cleanup actions only run when the component is actually unmounting and avoids unnecessary cleanup attempts during rapid component updates.