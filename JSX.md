# Description of JSX

JSX (JavaScript XML) is a syntax extension for JavaScript that allows writing HTML-like code inside React components. It makes defining UI components more intuitive and readable. JSX gets compiled into React.createElement() calls behind the scenes.

# Example of JSX

A React component that renders a greeting message:
const Greeting = () => {
const name = "John";
return <h1>Hello, {name}!</h1>;
};

export default Greeting;

# Common Mistakes to Avoid with JSX

Forgetting to Wrap Multiple Elements in a Parent Container
_ JSX expressions must return a single parent element.
Using JavaScript Expressions Without Curly Braces
_ JSX allows embedding JavaScript expressions inside {}.
Using class Instead of className
_In JSX, class is a reserved JavaScript keyword, so use className.
Using if Statements Inside JSX Instead of Ternary Operators
_ JSX does not support if statements directly inside markup.
Not Closing Self-Closing Tags \* JSX requires self-closing tags for elements like <img>, <input>, etc.

Returning Multiple Lines Without Parentheses \* When returning multiple lines, wrap them in parentheses to avoid syntax errors.
