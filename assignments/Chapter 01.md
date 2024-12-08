# Chapter 01 - Inception

### 1. What is Emmet ?

Emmet is like a shortcut tool for writing HTML and CSS faster.

It lets you type short codes (called abbreviations), and when you press a key(usually `Tab` or `Enter`), it expands them into full HTML or CSS code. 

Ex: You type: `div.container>ul>li*3` 

Press `Tab`, and it becomes: 

```html
<div class="container">
    <ul>
        <li></li>
        <li></li>
        <li></li>
    </ul>
</div>
```

It’s built into many code editors (like VS Code) and saves a lot of time by avoiding repetitive typing 

### 2. Difference between a Library and Framework ?

A **library** is like a toolbox. It gives you pre-written code (tools) to help you solve specific problems or perform certain tasks. You decide when and how to use it in your code. You are in control.

**Framework** is like a structure or template for building a house. It gives you a foundation and expects you to build your application following its rules and patterns. It is in control.

### 3. What is CDN ? Why do we use it ?

**CDN (Content Delivery Network)** is a system of servers located around the world that delivers content (like images, videos, CSS, JavaScript, etc.) to users quickly and efficiently.

**Why do we use it?**

1. **Faster Loading**: CDNs serve content from the server closest to the user, reducing delays.
2. **Reduced Server Load**: Offloads traffic from your main server to CDN servers.
3. **Global Reach**: Makes your website faster for users worldwide.
4. **Better Reliability**: If one server fails, others take over.
5. **Improved SEO**: Faster websites rank better on search engines.

### 4. Why is React known as React ?

React is called "React" because it is designed to **react** to changes in data efficiently. When the data in your application changes, React "reacts" by automatically updating the user interface (UI) to reflect those changes, without reloading the entire page.

This reactive nature comes from its use of a **virtual DOM**. React calculates the minimum updates needed to make the UI match the new state, making it fast and responsive.

### 5. What is crossorigin in script tag ?

The `crossorigin` attribute in a `<script>` tag specifies how the browser handles cross-origin requests for the script. It determines whether the script should be fetched with credentials like cookies or whether it should allow sharing error details for security purposes.

The `crossorigin` attribute is often used with:

- **CORS (Cross-Origin Resource Sharing):** Ensures scripts from other origins comply with security policies.
- **Subresource Integrity (SRI):** Allows the browser to verify the script's integrity without exposing credentials.

```html
<script src="https://example.com/script.js" integrity="sha384-abc123" crossorigin="anonymous"></script>
```

### 6. What is difference between React and ReactDOM ?

React is a core library for building user interfaces. Provides the tools to create components, manage state, and handle UI logic. It enables writing JSX and handle the virtual DOM for efficient rendering.

ReactDOM is a library works alongside React, specifically for interacting with the actual DOM. It connects react components to the browser’s real DOM

```jsx
// Import React for creating components
import React from 'react';
// Import ReactDOM for rendering components
import ReactDOM from 'react-dom/client';

// React Component
function App() {
  return <h1>Hello, React!</h1>;
}

// ReactDOM renders the App component into the real DOM
const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(<App />);
```

### 7. What is difference between react.development.js and react.production.js files via CDN ?

**react.development.js** is designed for development environments.

- Includes detailed error messages and warnings to help with debugging.
- Provides helpful developer tools and checks
- Larger in size due to the extra debugging features.

```jsx
<script src="https://unpkg.com/react@latest/umd/react.development.js"></script>
```

**react.production.js is designed for production environments.**

- Stripped of debugging tools and warnings to reduce file size.
- Minimized and optimized for better performance.
- No developer-focused logs or checks.

```jsx
<script src="https://unpkg.com/react@latest/umd/react.production.min.js"></script>
```

### 8. What is async and defer ?

The `async` and `defer` attributes in the `<script>` tag control how scripts are loaded and executed in relation to the HTML parsing process. Both are used to improve page load performance, but they behave differently.

1. **async:** 
- The script is downloaded **asynchronously** while the HTML is being parsed.
- Once the script is fully downloaded, it is executed **immediately**, pausing HTML parsing.
- **Best for**: Scripts that don't depend on each other or the HTML structure.
- **Drawback**: If multiple scripts have `async`, they may execute in a non-deterministic order.
2. **defer** 
- The script is downloaded **asynchronously** while the HTML is being parsed.
- The script is executed **only after** the entire HTML document has been parsed.
- Scripts with `defer` are executed in the order they appear in the document.
- **Best for**: Scripts that rely on the full HTML structure or need to execute in a specific order.