# Events

React events are similar to native DOM events but follow a synthetic event system that ensures consistency across different browsers. Events are handled using camelCase properties (e.g., onClick, onChange) and can be controlled using functions.

# Simple Example of an Event in React

A button that updates the count when clicked:

import { useState } from "react";

const Counter = () => {
const [count, setCount] = useState(0);

const handleClick = () => {
setCount(count + 1);
};

return (
<div>
<p>Count: {count}</p>
<button onClick={handleClick}>Increase</button>
</div>
);
};

export default Counter;

# Common Mistakes to Avoid with React Events

Calling Event Handlers Instead of Passing Them as Functions

Forgetting to Use an Arrow Function for Event Handlers With Arguments

Not Preventing Default Behavior for Events Like Form Submissions

Modifying Event Object After an Asynchronous Operation

Not Using useCallback for Performance Optimization in Frequent Event Handlers
