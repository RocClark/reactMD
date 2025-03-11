# Description of React Portals

React Portals allow rendering a component outside its normal parent hierarchy while keeping it part
of the React tree. This is useful for modals, tooltips, popups, or other Ul elements that should not be
confined by CSS overflow or z-index issues.

#Example of a Portal
import React from "react";
import ReactDOM from "react-dom";

const Modal = ({ children, onClose }) => {
return ReactDOM.createPortal(

<div className="modal-overlay" onClick={onClose}>
<div className="modal-content" onClick={(e) => e.stopPropagation()}>
{children}
<button onClick={onClose}>Close</button>
</div>
</div>,
document.getElementById("modal-root") // Renders outside the normal DOM tree
);
};

export default Modal;

# Usage in a component:

const App = () => {
const [isOpen, setIsOpen] = React.useState(false);

return (

<div>
<button onClick={() => setIsOpen(true)}>Open Modal</button>
{isOpen && <Modal onClose={() => setIsOpen(false)}>Hello, Portal!</Modal>}
<div id="modal-root"></div> {/_ Ensure this div exists in your HTML _/}
</div>
);
};

export default App;

# Common Mistakes to Avoid with Portals

Forgetting to Add the Portal Target (#modal-root) in index.html \* The portal needs an existing DOM node to attach to.

Not Preventing Click Events from Bubbling \* Clicking inside a modal might accidentally trigger its close handler.

Not Handling Unmount Cleanup \* If the modal has event listeners (e.g., keydown for Escape key), clean them up on unmount.

Using Portals When Not Necessary \* Portals are great for modals, tooltips, and dropdowns, but not every UI element needs a portal.

Forgetting to Style the Portal Elements Properly \* Since portals are rendered outside their normal hierarchy, CSS styles like position: fixed may need adjustments.
