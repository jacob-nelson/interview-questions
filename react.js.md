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


### what is suspense?
[Suspense](https://react.dev/reference/react/Suspense)
