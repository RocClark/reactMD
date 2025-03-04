# Effects

useEffect is a React hook that allows you to run side effects in functional components. It is commonly used for fetching data, updating the DOM, setting up subscriptions, and handling timers.

# Simple Example of useEffect

A component that logs a message when it mounts and updates the document title when the count changes:

import { useState, useEffect } from "react";

const Counter = () => {
const [count, setCount] = useState(0);

useEffect(() => {
console.log("Component mounted");
}, []); // Runs only on mount

useEffect(() => {
document.title = `Count: ${count}`;
}, [count]); // Runs when `count` changes

return (
<div>
<p>Count: {count}</p>
<button onClick={() => setCount(count + 1)}>Increase</button>
</div>
);
};

export default Counter;

# Common Mistakes to Avoid with useEffect

Not Providing a Dependency Array

Incorrectly Using Dependencies in the Dependency Array

Not Cleaning Up Effects

Updating State Inside useEffect Without Handling Infinite Loops
