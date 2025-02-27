# Brief Description of React Components

React components are reusable, self-contained pieces of UI that can be class-based or functional. They allow developers to build complex interfaces by composing smaller, manageable parts. Components can accept inputs called props and manage their own internal state using useState or other hooks.

# Simple Example

import { useState } from "react";

const Counter = () => {
const [count, setCount] = useState(0);

return (
<div>
<p>Count: {count}</p>
<button onClick={() => setCount(count + 1)}>Increase</button>
</div>
);
};

export default Counter;

# Common Mistakes to Avoid

Modifying State Directly

Not Wrapping Event Handlers in Functions

Using Index as Key in Lists

Not Cleaning Up Effects in useEffect

Passing Unnecessary Props
When using useEffect for subscriptions or timers, always clean them up to avoid memory leaks.

Keep components clean by only passing necessary props to avoid unnecessary re-renders.
