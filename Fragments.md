# Description of React Fragments

React Fragments (<></> or <React.Fragment>) allow you to group multiple elements without adding an extra DOM node. This helps keep the markup clean and avoids unnecessary nesting.

# Simple Example of a Fragment

A component that returns multiple elements without wrapping them in an unnecessary <div>:

const UserInfo = () => {
return (
<>
<h2>John Doe</h2>
<p>Email: john@example.com</p>
</>
);
};

export default UserInfo;

# Common Mistakes to Avoid with Fragments

Unnecessary <div> Wrappers Instead of Using Fragments
* Wrapping elements in an extra <div> can cause unwanted layout issues, especially in flexbox or grid layouts.
Forgetting That Empty Fragments (<>) Cannot Have Keys
*If you need to use keys in lists, use <React.Fragment> instead of <>.
Using Fragments Where a Single Parent Element is Needed
\*Some elements (like <table>, <ul>, or <select>) require a specific structure.
