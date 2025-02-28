# Front-End-Developer-Role-

1. Null vs Undefined in JavaScript
undefined: A variable that has been declared but not assigned a value.
null: A variable explicitly set to have no value.
javascript

let a; // Not assigned a value
console.log(a); // Output: undefined

let b = null; // Explicitly set to null
console.log(b); // Output: null
2. Event Delegation in JavaScript
Event delegation allows you to handle events efficiently by adding a listener to a parent element and responding to events triggered by its child elements.
javascript

document.getElementById('parentElement').addEventListener('click', function(event) {
    if (event.target.tagName === 'LI') {
        console.log(`You clicked: ${event.target.innerText}`);
    }
});
3. CSS Display Properties
Inline: Takes only as much width as needed, cannot set height/width.
Block: Takes full width, starts on a new line.
Inline-block: Acts like inline but allows width/height settings.
Flex: Used to create flexible layouts.
css

.inline-example {
    display: inline;
    background: lightblue;
}

.block-example {
    display: block;
    width: 200px;
    background: lightgreen;
}

.inline-block-example {
    display: inline-block;
    width: 100px;
    height: 50px;
    background: coral;
}

.flex-container {
    display: flex;
    justify-content: space-between;
}
4. CSS Specificity
Specificity determines which styles are applied when multiple rules exist.
css

/* Specificity: 10 */
.example-class {
    color: blue;
}

/* Specificity: 11 (higher) */
p.example-class {
    color: red;
}

/* Specificity: 100 */
#unique-id {
    color: green;
}
5. CORS (Cross-Origin Resource Sharing)
CORS allows restricted resources to be accessed from a different origin.
Server-side solution (Node.js with Express):

javascript

const express = require('express');
const cors = require('cors');
const app = express();

app.use(cors()); // Enable CORS for all routes
app.get('/data', (req, res) => {
    res.json({ message: "CORS enabled" });
});

app.listen(3000);
6. CSS Preprocessors (SASS)
SASS allows variables, nesting, and functions.
scss

$primary-color: blue;

.button {
    background: $primary-color;
    &:hover {
        background: darken($primary-color, 10%);
    }
}
7. Closure in JavaScript
Closures allow inner functions to retain access to their outer function’s variables.
javascript

function outer() {
    let count = 0;
    return function inner() {
        count++;
        return count;
    };
}

let increment = outer();
console.log(increment()); // 1
console.log(increment()); // 2
8. localStorage vs sessionStorage
localStorage persists data indefinitely.
sessionStorage persists data only for the session.
javascript

localStorage.setItem("username", "JohnDoe");
console.log(localStorage.getItem("username")); // Output: JohnDoe

sessionStorage.setItem("sessionID", "12345");
console.log(sessionStorage.getItem("sessionID")); // Output: 12345
9. Web Components
Web Components are reusable, encapsulated HTML elements.
javascript

class MyComponent extends HTMLElement {
    connectedCallback() {
        this.innerHTML = `<p>Hello, this is a Web Component!</p>`;
    }
}
customElements.define('my-component', MyComponent);
html

<my-component></my-component>
10. Responsive Design
Using media queries to adapt to screen sizes.
css

.container {
    width: 100%;
}

@media (max-width: 600px) {
    .container {
        background: lightgray;
    }
}
11. GET vs POST HTTP Methods
GET retrieves data.
POST submits data.
javascript

// GET Request
fetch('https://api.example.com/data')
    .then(response => response.json())
    .then(data => console.log(data));

// POST Request
fetch('https://api.example.com/data', {
    method: 'POST',
    body: JSON.stringify({ name: "John" }),
    headers: { "Content-Type": "application/json" }
});
12. data- Attributes in HTML5
Storing custom data attributes.
html

<div id="myDiv" data-user-id="123">User</div>
<script>
    let userId = document.getElementById('myDiv').dataset.userId;
    console.log(userId); // Output: 123
</script>
13. Asynchronous JavaScript
Using callbacks, promises, async/await.
javascript

// Callback
function fetchData(callback) {
    setTimeout(() => callback('Data received'), 1000);
}

// Promise
function fetchDataPromise() {
    return new Promise(resolve => setTimeout(() => resolve('Data received'), 1000));
}

// Async/Await
async function fetchDataAsync() {
    let result = await fetchDataPromise();
    console.log(result);
}
fetchDataAsync();
14. Box-Sizing in CSS
Controls how width and height are calculated.
css

.box {
    width: 200px;
    padding: 20px;
    box-sizing: border-box;
}
15. Document Object Model (DOM)
DOM represents page structure as a tree.
javascript

document.getElementById('myElement').innerText = "Updated Text";
16. Progressive Enhancement
Build for basic functionality first, then enhance.
html

<noscript>
    <p>Please enable JavaScript for full functionality.</p>
</noscript>
17. Website Performance Optimization
Minimize HTTP requests, lazy loading, caching.
html

<img src="image.jpg" loading="lazy" alt="Optimized image">
18. Handling Browser Compatibility
Use feature detection and polyfills.
javascript

if (!window.fetch) {
    console.log("Fetch API not supported, loading polyfill...");
    // Load fetch polyfill
}
