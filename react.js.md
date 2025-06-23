### What is React?

React is a front-end and open-source JavaScript library which is useful in developing user interfaces specifically for applications with a single page. It is helpful in building complex and reusable user interface(UI) components of mobile and web applications as it follows the component-based approach.

The important features of React are:

- It supports server-side rendering.
- It will make use of the virtual DOM rather than real DOM (Data Object Model) as RealDOM manipulations are expensive.
- It follows unidirectional data binding or data flow.
- It uses reusable or composable UI components for developing the view.

### What are the advantages of using React?

MVC is generally abbreviated as Model View Controller.

➢ **Use of Virtual DOM to improve efficiency:** React uses virtual DOM to render the view. As the name suggests, virtual DOM is a virtual representation of the real DOM. Each time the data changes in a react app, a new virtual DOM gets created. Creating a virtual DOM is much faster than rendering the UI inside the browser. Therefore, with the use of virtual DOM, the efficiency of the app improves.  
➢ **Gentle learning curve:** React has a gentle learning curve when compared to frameworks like Angular. Anyone with little knowledge of javascript can start building web applications using React.  
➢ **SEO friendly:** React allows developers to develop engaging user interfaces that can be easily navigated in various search engines. It also allows server-side rendering, which boosts the SEO of an app.  
➢ **Reusable components:** React uses component-based architecture for developing applications. Components are independent and reusable bits of code. These components can be shared across various applications having similar functionality. The re-use of components increases the pace of development.  
➢ **Huge ecosystem of libraries to choose from:** React provides you with the freedom to choose the tools, libraries, and architecture for developing an application based on your requirement.

### What are the limitations of React?

The few limitations of React are as given below:

- React is not a full-blown framework as it is only a library.
- The components of React are numerous and will take time to fully grasp the benefits of all.
- It might be difficult for beginner programmers to understand React.
- Coding might become complex as it will make use of inline templating and JSX.

### What is useState() in React?

The `useState()` is a built-in React Hook that allows you for having state variables in functional components. It should be used when the DOM has something that is dynamically manipulating/controlling.

```jsx
import { useState } from 'react';

export default function CounterExample() {
  // useState returns an array with two elements:
  // 1. The current state value
  // 2. A function to update the state
  const [count, setCount] = useState(0);
  const [name, setName] = useState('');
  const [isVisible, setIsVisible] = useState(true);

  return (
    <div className="max-w-md mx-auto mt-8 p-6 bg-white rounded-lg shadow-lg">
      <h1 className="text-2xl font-bold mb-6 text-gray-800">useState Examples</h1>
      
      {/* Counter Example */}
      <div className="mb-6 p-4 border rounded-lg">
        <h2 className="text-lg font-semibold mb-3">Counter</h2>
        <p className="mb-3 text-gray-600">Count: {count}</p>
        <div className="space-x-2">
          <button 
            onClick={() => setCount(count + 1)}
            className="px-4 py-2 bg-blue-500 text-white rounded hover:bg-blue-600"
          >
            Increment
          </button>
          <button 
            onClick={() => setCount(count - 1)}
            className="px-4 py-2 bg-red-500 text-white rounded hover:bg-red-600"
          >
            Decrement
          </button>
          <button 
            onClick={() => setCount(0)}
            className="px-4 py-2 bg-gray-500 text-white rounded hover:bg-gray-600"
          >
            Reset
          </button>
        </div>
      </div>

      {/* Text Input Example */}
      <div className="mb-6 p-4 border rounded-lg">
        <h2 className="text-lg font-semibold mb-3">Text Input</h2>
        <input
          type="text"
          value={name}
          onChange={(e) => setName(e.target.value)}
          placeholder="Enter your name"
          className="w-full p-2 border rounded mb-2"
        />
        <p className="text-gray-600">
          {name ? `Hello, ${name}!` : 'Please enter your name'}
        </p>
      </div>

      {/* Toggle Example */}
      <div className="p-4 border rounded-lg">
        <h2 className="text-lg font-semibold mb-3">Toggle Visibility</h2>
        <button
          onClick={() => setIsVisible(!isVisible)}
          className="px-4 py-2 bg-green-500 text-white rounded hover:bg-green-600 mb-3"
        >
          {isVisible ? 'Hide' : 'Show'} Message
        </button>
        {isVisible && (
          <div className="p-3 bg-green-100 border border-green-300 rounded">
            <p className="text-green-800">This message can be toggled!</p>
          </div>
        )}
      </div>
    </div>
  );
}
```

### What are keys in React?

A key is a special string attribute that needs to be included when using lists of elements.

*Why Keys Matter*
Keys help React identify which items have changed, been added, or removed. This enables efficient updates and preserves component state.

✅ Key Best Practices:

- Use unique, stable IDs (like database IDs)
- Don't use array indices if the list can change
- Keys should be consistent between renders
- Keys only need to be unique among siblings
- Don't generate keys on the fly (Math.random(), Date.now())

```jsx
import { useState } from 'react';

export default function ReactKeyExample() {
  const [items, setItems] = useState([
    { id: 1, name: 'Apple', color: 'red' },
    { id: 2, name: 'Banana', color: 'yellow' },
    { id: 3, name: 'Orange', color: 'orange' }
  ]);
  
  const [newItem, setNewItem] = useState('');
  const [counter, setCounter] = useState(4);

  const addItem = () => {
    if (newItem.trim()) {
      const colors = ['red', 'blue', 'green', 'purple', 'pink'];
      const randomColor = colors[Math.floor(Math.random() * colors.length)];
      
      setItems([
        { id: counter, name: newItem, color: randomColor },
        ...items
      ]);
      setNewItem('');
      setCounter(counter + 1);
    }
  };

  const removeItem = (id) => {
    setItems(items.filter(item => item.id !== id));
  };

  const shuffleItems = () => {
    const shuffled = [...items].sort(() => Math.random() - 0.5);
    setItems(shuffled);
  };

  return (
    <div className="max-w-2xl mx-auto mt-8 p-6 bg-white rounded-lg shadow-lg">
      <h1 className="text-2xl font-bold mb-6 text-gray-800">React Key Example</h1>

      {/* Add new item */}
      <div className="mb-6 p-4 border rounded-lg">
        <h3 className="font-semibold mb-3">Add New Item</h3>
        <div className="flex gap-2">
          <input
            type="text"
            value={newItem}
            onChange={(e) => setNewItem(e.target.value)}
            placeholder="Enter item name"
            className="flex-1 p-2 border rounded"
            onKeyPress={(e) => e.key === 'Enter' && addItem()}
          />
          <button
            onClick={addItem}
            className="px-4 py-2 bg-green-500 text-white rounded hover:bg-green-600"
          >
            Add
          </button>
        </div>
      </div>

      {/* Controls */}
      <div className="mb-6">
        <button
          onClick={shuffleItems}
          className="px-4 py-2 bg-purple-500 text-white rounded hover:bg-purple-600 mr-2"
        >
          Shuffle Items
        </button>
        <span className="text-sm text-gray-600">
          Notice how input focus is preserved when shuffling
        </span>
      </div>

      {/* Items list with proper keys */}
      <div className="space-y-3">
        <h3 className="font-semibold">Items (with proper keys):</h3>
        {items.map((item) => (
          <div
            key={item.id} // ✅ Using unique, stable ID as key
            className="flex items-center justify-between p-3 border rounded-lg bg-gray-50"
          >
            <div className="flex items-center gap-3">
              <div
                className="w-4 h-4 rounded-full"
                style={{ backgroundColor: item.color }}
              ></div>
              <span className="font-medium">{item.name}</span>
              <input
                type="text"
                placeholder="Try typing here..."
                className="ml-2 p-1 text-xs border rounded"
              />
            </div>
            <button
              onClick={() => removeItem(item.id)}
              className="px-3 py-1 bg-red-500 text-white text-sm rounded hover:bg-red-600"
            >
              Remove
            </button>
          </div>
        ))}
      </div>

      {/* Bad example for comparison */}
      <div className="mt-8 p-4 bg-red-50 border border-red-200 rounded-lg">
        <h3 className="font-semibold mb-3 text-red-800">❌ Bad Example (using index as key):</h3>
        <p className="text-red-700 text-sm mb-3">
          This would cause issues when items are reordered or removed:
        </p>
        <div className="bg-gray-100 p-3 rounded font-mono text-sm">
          {`{items.map((item, index) => (
  <div key={index}> // ❌ BAD: using index
    {item.name}
  </div>
))}`}
        </div>
      </div>
    </div>
  );
}
```


### what is suspense?
[Suspense](https://react.dev/reference/react/Suspense)
