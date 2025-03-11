# Description of Props in React

Props (short for "properties") are a way to pass data from a parent component to a child component in React. They make components reusable and dynamic by allowing data to be customized. Props are read-only and should not be modified inside the child component.

# Example of Props

A component that displays a greeting message with a dynamic name:

const Greeting = ({ name }) => {
return <h1>Hello, {name}!</h1>;
};

const App = () => {
return <Greeting name="Alice" />; // Passing "Alice" as a prop
};

export default App;

# Common Mistakes to Avoid with Props

Modifying Props Inside a Component \* Props are immutable; modifying them inside a component causes unexpected behavior.

Forgetting to Pass Required Props \* If a prop is missing, it may cause errors or render incorrectly.

Passing Non-Serializable Data (like Functions) Incorrectly \* Be careful when passing functions as props to avoid unnecessary re-renders.

Passing Too Many Props (Prop Drilling) \* If a prop needs to be passed through many components, use Context API instead.

Using Boolean Props Incorrectly \* Boolean props don't need explicit true values in JSX.

Spreading Props Carelessly \* Spreading props can lead to unexpected behavior and security risks.
