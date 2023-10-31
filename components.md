# React Components

React applications are made of components.

## 1. What's a Component?

A component is a small, reusable chunk of code that is responsible for one job. That job is often to render some HTML and re-render it when some data changes.

Take a look at the code below. This code will create and render a new React component:

```jsx
import React from 'react';
import ReactDOM from 'react-dom/client';

function MyComponent() {
  return <h1>Hello world</h1>;
}

ReactDOM.createRoot(
  document.getElementById('app')
).render(<MyComponent />);
```

A lot of these look unfamiliar but do not worry. We are going to unpack that code, one small piece at a time. By the end of this lesson, you'll understand how to build a React component!

Certainly! Here's the provided information formatted in Markdown:

---

## 2. Import React

The first React component we created in the last exercise started with importing React. The line that did this is:

```jsx
import React from 'react';
```

This creates an object named `React`, which contains methods necessary to use the React library. `React` is imported from the 'react' package, which should be installed in your project as a dependency. With the `React` object, we can start utilizing features of the React library!

By importing the library, we can use important features such as Hooks, which we'll explore in detail later.

For the next few exercises, we'll be working in two files: `App.js` and `index.js`. In a React application, the `App.js` file typically is the top level of your application, and `index.js` is the entry point.


## 3. Import ReactDOM

Another import we need in addition to React is ReactDOM:

```jsx
import ReactDOM from 'react-dom/client';
```

The methods imported from 'react-dom' interact with the DOM.

The methods imported from 'react' do not deal with the DOM at all. They don't engage directly with anything that isn't part of React.

To clarify: the DOM is used in React applications, but it isn't part of React. After all, the DOM is also used in countless non-React applications. Methods imported from 'react' are only for pure React purposes, such as creating components or writing JSX elements.
