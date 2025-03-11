# Description of Keys in React

Keys in React are unique identifiers used to efficiently update and render lists of elements. They help React track which items have changed, been added, or removed, improving performance in dynamic lists.

# Example of Keys in a List

A component that renders a list of items using keys:
const ItemList = () => {
const items = ["Apple", "Banana", "Cherry"];

return (
<ul>
{items.map((item, index) => (
<li key={index}>{item}</li>
))}
</ul>
);
};

export default ItemList;

# Common Mistakes to Avoid with Keys

Using Index as a Key When Items Can Change

If items reorder, remove, or update, using the index as a key can cause incorrect re-renders.
