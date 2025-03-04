# Description of React Hooks

React Hooks are functions that let you use state and other React features in functional components without needing class components. Some common hooks include:

useState – for managing state
useEffect – for side effects
useContext – for global state management
useRef – for persisting values without causing re-renders
useMemo & useCallback – for performance optimizations

# Simple Example of a Hook (useState)

A component that uses useState to manage a counter:
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

# Common Mistakes to Avoid with Hooks

Using Hooks Inside Loops, Conditions, or Nested Functions
_ Hooks must be called at the top level of a function component and in the same order every time.
Forgetting to Include Dependencies in useEffect
_ Missing dependencies can lead to stale values or unexpected behavior.  
Updating State Without Considering Previous State
_ Always use a function when updating state based on the previous state.
Using useEffect When Not Necessary
_ Avoid unnecessary useEffect when a simple function call will do.
Mutating State Instead of Updating It Properly
_ Always create a new object or array instead of mutating the existing state.
Using useEffect Incorrectly for Fetching Data
_ Fetching inside useEffect should handle cleanup and async calls properly.
