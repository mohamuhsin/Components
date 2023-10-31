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


## 4. Create a Function Component

You've learned that a React component is a small, reusable chunk of code that is responsible for one job, which often involves rendering HTML and re-rendering it whenever some data changes.

It's useful to think of components as smaller pieces of our interface. Combined, they are the building blocks that make up a React application. In a website, we can create a component for the search bar, another component for the navigation bar, and another component for the dashboard content itself.

Here's another fact about components: we can use JavaScript functions to define a new React component. This is called a function component.

In the past, React components were defined using JavaScript classes. But since the introduction of Hooks (something we'll discuss later), function components have become the standard in modern React applications.

After we define our functional component, we can use it to create as many instances of that component as we want.

Let's take a look at the example from the first exercise:

```jsx
import React from 'react';

function MyComponent() {
  return <h1>Hello, I'm a functional React Component!</h1>;
}

export default MyComponent;
```

On the third line, a function is defined with the name `MyComponent`. Inside, the function returns a React element in JSX syntax:

```jsx
return <h1>Hello, I'm a functional React Component!</h1>;
```

Combined, this makes a basic React functional component.

On the last line of the above code block, `MyComponent` is exported so it can be used later.

A lot of it is still unfamiliar, but you can understand more than you could before! Let's keep going!


## 5. Name a Functional Component

Great! When creating a new functional component in JavaScript, you need to provide it with a name. In the example provided earlier, the component's name was "MyComponent":

```jsx
function MyComponent() {
  return <h1>Hello world</h1>;
}
```

It's important to note that function component names must start with capitalization, and conventionally, they are created using PascalCase. This naming convention is crucial because of how JSX tags are compiled. Capitalization indicates that it is a React component rather than an HTML tag.

This is a React-specific nuance! When creating a component, make sure to name it starting with a capital letter. This way, React will interpret it as a React component. If the name begins with a lowercase letter, React will assume you are referring to a built-in HTML component like `div` or `input` and may fail to recognize your custom component.
