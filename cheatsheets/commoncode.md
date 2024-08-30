# Common HTML and JavaScript Code Snippets

## Table of Contents

- [Introduction](#introduction)
- [HTML Snippets](#html-snippets)
  - [Basic HTML Structure](#basic-html-structure)
  - [Advanced Responsive HTML Structure](#advanced-responsive-html-structure)
  - [Navigation Bar](#navigation-bar)
  - [Responsive Image](#responsive-image)
  - [Form with Validation](#form-with-validation)
  - [Table with Sorting](#table-with-sorting)
  - [Modal Popup](#modal-popup)
  - [Dropdown Menu](#dropdown-menu)
- [JavaScript Snippets](#javascript-snippets)
  - [DOM Manipulation](#dom-manipulation)
  - [Event Handling](#event-handling)
  - [AJAX Request](#ajax-request)
  - [Debounce Function](#debounce-function)
  - [Local Storage](#local-storage)
  - [Form Validation](#form-validation)
- [Add New Code Blocks Here](#add-new-code-blocks-here)
- [Resources](#resources)

## Introduction

This cheat sheet contains common HTML and JavaScript code snippets that are frequently used in web development. It also includes sections for adding new code blocks as needed.

## HTML Snippets

### Basic HTML Structure

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <link rel="stylesheet" href="styles.css">
</head>
<body>
  <header>
    <h1>Welcome to My Website</h1>
  </header>
  <main>
    <section>
      <h2>Section Title</h2>
      <p>Content goes here...</p>
    </section>
  </main>
  <footer>
    <p>&copy; 2024 My Website. All rights reserved.</p>
  </footer>
  <script src="script.js"></script>
</body>
</html>
```

### Advanced Responsive HTML Structure

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Advanced Responsive Structure</title>
  <link rel="stylesheet" href="styles.css">
  <style>
    body {
      margin: 0;
      font-family: Arial, sans-serif;
    }
    .container {
      display: flex;
      flex-direction: column;
      min-height: 100vh;
    }
    header, footer {
      background: #333;
      color: #fff;
      padding: 1rem;
    }
    main {
      flex: 1;
      padding: 1rem;
    }
    .grid {
      display: grid;
      grid-template-columns: 1fr;
      gap: 1rem;
    }
    @media(min-width: 768px) {
      .grid {
        grid-template-columns: 1fr 1fr;
      }
    }
    @media(min-width: 1024px) {
      .grid {
        grid-template-columns: 1fr 1fr 1fr;
      }
    }
  </style>
</head>
<body>
  <div class="container">
    <header>
      <h1>Website Header</h1>
      <nav>
        <ul>
          <li><a href="#home">Home</a></li>
          <li><a href="#about">About</a></li>
          <li><a href="#services">Services</a></li>
          <li><a href="#contact">Contact</a></li>
        </ul>
      </nav>
    </header>
    <main>
      <section class="grid">
        <article>
          <h2>Article 1</h2>
          <p>Content for article 1...</p>
        </article>
        <article>
          <h2>Article 2</h2>
          <p>Content for article 2...</p>
        </article>
        <article>
          <h2>Article 3</h2>
          <p>Content for article 3...</p>
        </article>
      </section>
    </main>
    <footer>
      <p>&copy; 2024 My Website. All rights reserved.</p>
    </footer>
  </div>
  <script src="script.js"></script>
</body>
</html>
```

### Navigation Bar

```html
<nav>
  <ul>
    <li><a href="#home">Home</a></li>
    <li><a href="#services">Services</a></li>
    <li><a href="#contact">Contact</a></li>
  </ul>
</nav>
```

### Responsive Image

```html
<img src="image.jpg" alt="Description of image" style="max-width: 100%; height: auto;">
```

### Form with Validation

```html
<form id="myForm">
  <label for="email">Email:</label>
  <input type="email" id="email" name="email" required>
  <label for="password">Password:</label>
  <input type="password" id="password" name="password" required pattern=".{8,}">
  <input type="submit" value="Submit">
</form>
<script>
  document.getElementById('myForm').addEventListener('submit', function(event) {
    if (!this.checkValidity()) {
      event.preventDefault();
      alert('Please fill out the form correctly.');
    }
  });
</script>
```

### Table with Sorting

```html
<table id="myTable">
  <thead>
    <tr>
      <th onclick="sortTable(0)">Name</th>
      <th onclick="sortTable(1)">Age</th>
      <th onclick="sortTable(2)">Country</th>
    </tr>
  </thead>
  <tbody>
    <tr><td>John</td><td>25</td><td>USA</td></tr>
    <tr><td>Anna</td><td>30</td><td>Canada</td></tr>
    <tr><td>Mike</td><td>35</td><td>UK</td></tr>
  </tbody>
</table>
<script>
  function sortTable(n) {
    const table = document.getElementById("myTable");
    let rows, switching, i, x, y, shouldSwitch, dir, switchcount = 0;
    switching = true;
    dir = "asc";
    while (switching) {
      switching = false;
      rows = table.rows;
      for (i = 1; i < (rows.length - 1); i++) {
        shouldSwitch = false;
        x = rows[i].getElementsByTagName("TD")[n];
        y = rows[i + 1].getElementsByTagName("TD")[n];
        if (dir == "asc") {
          if (x.innerHTML.toLowerCase() > y.innerHTML.toLowerCase()) {
            shouldSwitch = true;
            break;
          }
        } else if (dir == "desc") {
          if (x.innerHTML.toLowerCase() < y.innerHTML.toLowerCase()) {
            shouldSwitch = true;
            break;
          }
        }
      }
      if (shouldSwitch) {
        rows[i].parentNode.insertBefore(rows[i + 1], rows[i]);
        switching = true;
        switchcount++;
      } else {
        if (switchcount == 0 && dir == "asc") {
          dir = "desc";
          switching = true;
        }
      }
    }
  }
</script>
```

### Modal Popup

```html
<!-- Trigger/Open The Modal -->
<button id="myBtn">Open Modal</button>

<!-- The Modal -->
<div id="myModal" class="modal">
  <!-- Modal content -->
  <div class="modal-content">
    <span class="close">&times;</span>
    <p>Some text in the Modal..</p>
  </div>
</div>

<style>
  /* The Modal (background) */
  .modal {
    display: none;
    position: fixed;
    z-index: 1;
    left: 0;
    top: 0;
    width: 100%;
    height: 100%;
    overflow: auto;
    background-color: rgb(0,0,0);
    background-color: rgba(0,0,0,0.4);
    padding-top: 60px;
  }

  /* Modal Content/Box */
  .modal-content {
    background-color: #fefefe;
    margin: 5% auto;
    padding: 20px;
    border: 1px solid #888;
    width: 80%;
  }

  /* The Close Button */
  .close {
    color: #aaa;
    float: right;
    font-size: 28px;
    font-weight: bold;
  }

  .close:hover,
  .close:focus {
    color: black;
    text-decoration: none;
    cursor: pointer;
  }
</style>

<script>
  // Get the modal
  var modal = document.getElementById("myModal");

  // Get the button that opens the modal
  var btn = document.getElementById("myBtn");

  // Get the <span> element that closes the modal
  var span = document.getElementsByClassName("close")[0];

  // When the user clicks the button, open the modal 
  btn.onclick = function() {
    modal.style.display = "block";
  }

  // When the user clicks on <span> (x), close the modal
  span.onclick = function() {
    modal.style.display = "none";
  }

  // When the user clicks anywhere outside of the modal, close it
  window.onclick = function(event) {
    if (event.target == modal) {
      modal.style.display = "none";
    }
  }
</script>
```

### Dropdown Menu

```html
<div class="dropdown">
  <button class="dropbtn">Dropdown</button>
  <div class="dropdown-content">
    <a href="#link1">Link 1</a>
    <a href="#link2">Link 2</a>
    <a href="#link3">Link 3</a>
  </div>
</div>

<style>
  .dropdown {
    position: relative;
    display: inline-block;
  }

  .dropbtn {
    background-color: #4CAF50;
    color: white;
    padding: 16px;
    font-size: 16px;
    border: none;
    cursor: pointer;
  }

  .dropdown-content {
    display: none;
    position: absolute;
    background-color: #f9f9f9;
    min-width: 160px;
    box-shadow: 0px 8px 16px 0px rgba(0,0,0,0.2);
    z-index: 1;
  }

  .dropdown-content a {
    color: black;
    padding: 12px 16px;
    text-decoration: none;
    display: block;
  }

  .dropdown-content a:hover {
    background-color: #f1f1f1;
  }

  .dropdown:hover .dropdown-content {
    display: block;
  }

  .dropdown:hover .dropbtn {
    background-color: #3e8e41;
  }
</style>
```

## JavaScript Snippets

### DOM Manipulation

```js
// Select an element
const element = document.getElementById('myElement');

// Change content
element.innerHTML = 'New Content';

// Change style
element.style.color = 'red';
```

### Event Handling

```js
// Add event listener
document.getElementById('myButton').addEventListener('click', function() {
  alert('Button clicked!');
});
```

### AJAX Request

```js
const xhr = new XMLHttpRequest();
xhr.open('GET', 'https://api.example.com/data', true);
xhr.onreadystatechange = function () {
  if (xhr.readyState === 4 && xhr.status === 200) {
    const data = JSON.parse(xhr.responseText);
    console.log(data);
  }
};
xhr.send();
```

### Debounce Function

```js
function debounce(func, wait) {
  let timeout;
  return function(...args) {
    const context = this;
    clearTimeout(timeout);
    timeout = setTimeout(() => func.apply(context, args), wait);
  };
}

// Usage
window.addEventListener('resize', debounce(function() {
  console.log('Resize event triggered!');
}, 250));
```

### Local Storage

```js
// Store data
localStorage.setItem('key', 'value');

// Retrieve data
const value = localStorage.getItem('key');
console.log(value);

// Remove data
localStorage.removeItem('key');

// Clear all data
localStorage.clear();
```

### Form Validation

```js
document.getElementById('myForm').addEventListener('submit', function(event) {
  const email = document.getElementById('email').value;
  const password = document.getElementById('password').value;

  if (!email || !password) {
    event.preventDefault();
    alert('Please fill out all fields.');
  } else if (password.length < 8) {
    event.preventDefault();
    alert('Password must be at least 8 characters long.');
  }
});
```

## Add New Code Blocks Here

### New HTML Code Block

```html
<!-- Add your new HTML code block here -->
```

### New JavaScript Code Block

```js
// Add your new JavaScript code block here
```

## Resources

- [MDN Web Docs](https://developer.mozilla.org/en-US/)
- [W3Schools](https://www.w3schools.com/)
- [JavaScript.info](https://javascript.info/)

