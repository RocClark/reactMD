# Brief Description of React Error Boundaries

Error boundaries are special React components that catch JavaScript errors in their child components during rendering, in lifecycle methods, and in constructors. They help prevent an entire React app from crashing due to errors in a single component.

Error boundaries only catch errors in class components (functional components must be wrapped in an error boundary).

# Simple Example

import { Component, ReactNode } from "react";

class ErrorBoundary extends Component<{ children: ReactNode }, { hasError: boolean }> {
constructor(props: { children: ReactNode }) {
super(props);
this.state = { hasError: false };
}

static getDerivedStateFromError() {
return { hasError: true };
}

componentDidCatch(error: Error, info: React.ErrorInfo) {
console.error("Error caught by boundary:", error, info);
}

render() {
if (this.state.hasError) {
return <h2>Something went wrong.</h2>;
}
return this.props.children;
}
}

export default ErrorBoundary;

# how to use it

<ErrorBoundary>
  <ProblematicComponent />
</ErrorBoundary>

# Common Mistakes to Avoid with Error Boundaries

Using Them in Functional Components Without Wrapping in a Class

Functional components cannot be error boundaries directly because they don’t have lifecycle methods like componentDidCatch.
Forgetting to Wrap Components That Might Fail

If a part of your app crashes and there’s no error boundary, React will unmount the entire app.
Expecting Error Boundaries to Catch All Errors

They only catch render-time errors. They do not catch:
Errors in event handlers
Errors in asynchronous code (e.g., setTimeout, fetch)
Errors in server-side rendering
Errors inside the error boundary itself
Not Providing a User-Friendly Fallback UI

Instead of a generic message, provide users with an option to retry or go back.
