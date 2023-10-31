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

## 6. Function Component Instructions

Let's review what you've learned so far by examining `App.js` and `index.js`:

1. On line 1 of `App.js` and `index.js`, `import React from 'react'` creates a JavaScript object. This object contains properties that are needed to make React work, such as `React.createElement()`.

2. On line 2 of `index.js`, `import ReactDOM from 'react-dom/client` creates another JavaScript object. This object contains methods that help React interact with the DOM, such as `ReactDOM.createRoot()`.

3. On line 3 of `App.js`, by writing a JavaScript function, a function component was defined. We can't see this component quite yet, as it's more of a factory that produces instances of itself when used. If we want to see it, we need to render it into the DOM.

4. Whenever you create a function component, you need to give that function component a name. That name should be written in Pascal case like this: `UpperCamelCase`.

5. Something that we haven't talked about yet is the body of your function component: the pair of curly braces after the function definition and all of the code between those curly braces.

   Like all JavaScript functions, this one needs a body. The body will act as a set of instructions, explaining to your function component how it should build a React component.

   Here's what your function body would look like on its own, without the rest of the function declaration syntax. Find it in `App.js`:

   ```jsx
   return <h1>Hello, this is a function component body.</h1>;
   ```

   That doesn't look like a set of instructions explaining how to build a React component! Yet that's exactly what it is.


## 7. The Return Keyword in Functional Components

When we define a functional component, we essentially create a factory that can build the appropriate combination of elements every time we reference its name. It builds this combination by following a set of instructions that you must provide.

If you're thinking, "That sounds just like what a regular JavaScript function is for," then you're right! Functional components can be thought of in a very similar vein to regular JavaScript functions, except that their job is to assemble a portion of the interface based on given instructions!

Let's talk a bit more about these instructions.

Firstly, these instructions should take the form of a function declaration body, delimited by curly braces, like this:

```jsx
function Button() {
  // Instructions go here, between the curly braces.
}
```

Our instructions can include a combination of markup, CSS, and JavaScript to produce the desired result. The one thing we must always include is a `return` statement.

The function is expected to produce JSX code that can be used to render something onto the browser screen. Thus, when we define functional components, we must return a JSX element.

```jsx
function BackButton() {
 return <button>Back To Home</button>;
}
```

Of course, this doesn't immediately render `<button>Back To Home</button>` onto the browser screen. We've only defined our component.

Let's continue to see how to render it and understand why the `return` statement is necessary!


## 8. Importing and Exporting React Components

Before we can use the component we've defined and have it rendered onto the DOM, there's some additional work to do.

As mentioned earlier, a React application typically consists of two core files: `App.js` and `index.js`. The `App.js` file serves as the top level of your application, while `index.js` acts as the entry point.

Since we've defined the component inside `App.js`, and `index.js` is the entry point, we need to export the component from `App.js` to `index.js` in order to render it.

React components are highly reusable, and we can keep our component pieces separated, organized, and reusable by placing them in separate files and exporting them to where we need them.

To export a component, we use the `export` declaration and specify whether it's a default or named export. In this case, we'll use a default export.

After defining the function component in `App.js`, we can export it as the default export like this:

```jsx
export default MyComponent;
```

Now, we can head into our `index.js` file to import our component from `App.js`:

```jsx
import MyComponent from './App';
```

This allows us to use `MyComponent` in `index.js`.


## 9. Using and Rendering a Component

Now that we have a defined function component, we can start using it.

We can use it with an HTML-like syntax that resembles a self-closing tag:

```jsx
<MyComponent />
```

If you need to nest other components in between, you may also use an opening and corresponding closing tag structure:

```jsx
<MyComponent>
  <OtherComponent />
</MyComponent>
```

However, to render our component to the browser, we must rely on the `.createRoot()` and `.render()` methods from the React DOM library. This should be done in our entry point, `index.js`.

First, we call the `createRoot` method to create a React root container for displaying content. React applications typically have a single root DOM node, and everything inside it is managed by React DOM.

In other words, we give `createRoot` a DOM element to render in, and React will take over managing the DOM inside it.

Here's an example:

```jsx
ReactDOM.createRoot(document.getElementById('app'));
```

Let's break it down a bit further:

- `document.getElementById('app')` returns a DOM element from `index.html`.
- `.createRoot()` receives the DOM element as the first argument and creates a root for it.
- `.createRoot()` returns a reference to the root container on which you can call methods like `.render()`.

After the root is created, all that's left to do is call the `.render()` method on the returned root and display the React component like so:

```jsx
ReactDOM.createRoot(document.getElementById('app')).render(<MyComponent />);
```

From here, React will display `<MyComponent />` in the root and make it appear on the screen.

In an application fully built with React, you will only need to do this once. Once this is set up, React will manage the DOM of your application, and any updates to the UI are taken care of efficiently. Adding more components should take place in your top-level `App.js` file.


# Components and Advanced JSX
