# Context

React Context is a way to share state and values between components without having to pass props manually at every level. It is useful for managing global states like themes, authentication, or user preferences.

# Example

A ThemeContext that provides a dark or light theme:

import { createContext, useContext, useState, ReactNode } from "react";

const ThemeContext = createContext<{ theme: string; toggleTheme: () => void } | undefined>(undefined);

export const ThemeProvider = ({ children }: { children: ReactNode }) => {
const [theme, setTheme] = useState("light");

const toggleTheme = () => {
setTheme((prev) => (prev === "light" ? "dark" : "light"));
};

return <ThemeContext.Provider value={{ theme, toggleTheme }}>{children}</ThemeContext.Provider>;
};

export const useTheme = () => {
const context = useContext(ThemeContext);
if (!context) {
throw new Error("useTheme must be used within a ThemeProvider");
}
return context;
};

# Using the Context in a Component

const ThemeToggle = () => {
const { theme, toggleTheme } = useTheme();

return (
<button onClick={toggleTheme} className={`p-2 ${theme === "dark" ? "bg-gray-800 text-white" : "bg-gray-200"}`}>
Toggle Theme
</button>
);
};

# Wrapping the App with the Provider

import { ThemeProvider } from "./ThemeContext";

function App() {
return (
<ThemeProvider>
<ThemeToggle />
</ThemeProvider>
);
}

export default App;

# Common Mistakes

Forgetting to Wrap Components with the Provider

Not Checking If Context is undefined in Custom Hooks

Unnecessary Re-Renders Due to Context Changes

Overusing Context for Local State
