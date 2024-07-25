# HTML5 Cheat Sheet

## Table of Contents

- [Introduction](#introduction)
- [New Semantic Elements](#new-semantic-elements)
- [Forms](#forms)
- [Media Elements](#media-elements)
- [Canvas API](#canvas-api)
- [Local Storage](#local-storage)
- [Geolocation](#geolocation)
- [Web Workers](#web-workers)
- [Resources](#resources)
- [Summary Table](#summary-table)

## Introduction

HTML5 introduces new elements and APIs that make it easier to create rich web applications. This cheat sheet covers the most important features of HTML5, including new semantic elements, forms, media elements, the Canvas API, local storage, geolocation, and web workers.

## New Semantic Elements

HTML5 introduces new semantic elements that help structure the content of a webpage in a meaningful way. These elements provide better accessibility, SEO, and readability.

- **header**
  - Represents introductory content or a set of navigational links. It can contain headings, logo, navigation, and other introductory elements.

```html
<header>
  <h1>Website Title</h1>
  <nav>
    <ul>
      <li><a href="#home">Home</a></li>
      <li><a href="#about">About</a></li>
      <li><a href="#contact">Contact</a></li>
    </ul>
  </nav>
</header>
```

- **nav**
  - Represents a section of a page intended for navigation. It can contain a list of links to other sections of the website or external sites.

```html
<nav>
  <ul>
    <li><a href="#home">Home</a></li>
    <li><a href="#services">Services</a></li>
    <li><a href="#contact">Contact</a></li>
  </ul>
</nav>
```

- **section**
  - Represents a standalone section of content, typically with a heading. It is used to group related content together.

```html
<section>
  <h2>Our Services</h2>
  <p>We offer a variety of services to help you achieve your goals...</p>
</section>
```

- **article**
  - Represents a self-contained piece of content that can be independently distributed or reused. It is commonly used for blog posts, news articles, or user-generated content.

```html
<article>
  <h2>Blog Post Title</h2>
  <p>Blog post content...</p>
</article>
```

- **aside**
  - Represents content that is tangentially related to the content around it. It is often used for sidebars, pull quotes, or advertisements.

```html
<aside>
  <h2>Related Articles</h2>
  <ul>
    <li><a href="#article1">Article 1</a></li>
    <li><a href="#article2">Article 2</a></li>
  </ul>
</aside>
```

- **footer**
  - Represents the footer of a section or page. It typically contains metadata, links to related documents, or navigation links.

```html
<footer>
  <p>&copy; 2024 My Website. All rights reserved.</p>
  <nav>
    <ul>
      <li><a href="#privacy">Privacy Policy</a></li>
      <li><a href="#terms">Terms of Service</a></li>
    </ul>
  </nav>
</footer>
```

- **main**
  - Represents the main content of the document. There should only be one `main` element per document, and it should not be a descendant of `article`, `aside`, `footer`, `header`, or `nav`.

```html
<main>
  <h1>Welcome to Our Website</h1>
  <p>This is the main content of the website...</p>
</main>
```

- **figure**
  - Represents self-contained content, such as illustrations, diagrams, photos, code listings, etc. The content of the figure should be referenced from the main flow of the document.

```html
<figure>
  <img src="image.jpg" alt="Description of image">
  <figcaption>Caption for the image</figcaption>
</figure>
```

- **figcaption**
  - Provides a caption or legend for the content of its parent `figure` element.

```html
<figure>
  <img src="image.jpg" alt="Description of image">
  <figcaption>Caption for the image</figcaption>
</figure>
```

- **mark**
  - Represents highlighted text for reference purposes, due to its relevance in another context.

```html
<p>This is a <mark>highlighted</mark> text.</p>
```

- **time**
  - Represents a specific period in time. Can include a `datetime` attribute to specify a machine-readable version of the date and time.

```html
<p>The event starts at <time datetime="2024-07-24T19:00">7:00 PM on July 24, 2024</time>.</p>
```

## Forms

HTML5 introduces new form elements and input types to improve the user experience and validation.

- **New Input Types**
  - `email`, `url`, `number`, `range`, `date`, `datetime-local`, `month`, `week`, `time`, `search`, `tel`, `color`.

```html
<form>
  <label for="email">Email:</label>
  <input type="email" id="email" name="email">
  
  <label for="date">Date:</label>
  <input type="date" id="date" name="date">
  
  <label for="color">Favorite Color:</label>
  <input type="color" id="color" name="color">
  
  <input type="submit" value="Submit">
</form>
```

- **New Attributes**
  - `autocomplete`, `autofocus`, `placeholder`, `required`, `pattern`, `min`, `max`, `step`.

```html
<form>
  <label for="username">Username:</label>
  <input type="text" id="username" name="username" placeholder="Enter your username" required>
  
  <label for="age">Age:</label>
  <input type="number" id="age" name="age" min="1" max="120">
  
  <input type="submit" value="Submit">
</form>
```

## Media Elements

HTML5 introduces new elements for embedding audio and video content.

- **audio**
  - Used to embed audio content.

```html
<audio controls>
  <source src="audio-file.mp3" type="audio/mpeg">
  Your browser does not support the audio element.
</audio>
```

- **video**
  - Used to embed video content.

```html
<video controls width="600">
  <source src="video-file.mp4" type="video/mp4">
  Your browser does not support the video element.
</video>
```

## Canvas API

The Canvas API provides a means for drawing graphics via JavaScript. It can be used for drawing graphs, making photo compositions, creating animations, and even doing real-time video processing or rendering game graphics.

- **canvas**
  - Used to define a drawing area in HTML.

```html
<canvas id="myCanvas" width="500" height="400" style="border:1px solid #000000;"></canvas>
```

- **Drawing on Canvas**

```js
const canvas = document.getElementById('myCanvas');
const ctx = canvas.getContext('2d');

// Draw a rectangle
ctx.fillStyle = '#FF0000';
ctx.fillRect(20, 20, 150, 100);

// Draw a circle
ctx.beginPath();
ctx.arc(240, 160, 60, 0, 2 * Math.PI);
ctx.fillStyle = '#00FF00';
ctx.fill();
ctx.stroke();

// Draw a line
ctx.beginPath();
ctx.moveTo(300, 50);
ctx.lineTo(450, 200);
ctx.strokeStyle = '#0000FF';
ctx.stroke();
```

## Local Storage

HTML5 provides the Web Storage API, which includes `localStorage` and `sessionStorage`. These allow you to store data on the client's computer.

- **localStorage**
  - Stores data with no expiration date.

```js
// Store data
localStorage.setItem('username', 'JohnDoe');

// Retrieve data
const username = localStorage.getItem('username');

// Remove data
localStorage.removeItem('username');

// Clear all data
localStorage.clear();
```

- **sessionStorage**
  - Stores data for the duration of the page session.

```js
// Store data
sessionStorage.setItem('username', 'JohnDoe');

// Retrieve data
const username = sessionStorage.getItem('username');

// Remove data
sessionStorage.removeItem('username');

// Clear all data
sessionStorage.clear();
```

## Geolocation

The Geolocation API allows you to retrieve the geographical location of the user.

```js
if (navigator.geolocation) {
  navigator.geolocation.getCurrentPosition(showPosition, showError);
} else {
  console.log('Geolocation is not supported by this browser.');
}

function showPosition(position) {
  const lat = position.coords.latitude;
  const lon = position.coords.longitude;
  console.log(`Latitude: ${lat}, Longitude: ${lon}`);
}

function showError(error) {
  switch(error.code) {
    case error.PERMISSION_DENIED:
      console.log('User denied the request for Geolocation.');
      break;
    case error.POSITION_UNAVAILABLE:
      console.log('Location information is unavailable.');
      break;
    case error.TIMEOUT:
      console.log('The request to get user location timed out.');
      break;
    case error.UNKNOWN_ERROR:
      console.log('An unknown error occurred.');
      break;
  }
}
```

## Web Workers

The Web Workers API allows you to run scripts in background threads.

```js
// Create a new web worker
const worker = new Worker('worker.js');

// Send data to the worker
worker.postMessage('Hello, worker');

// Receive messages from the worker
worker.onmessage = function(event) {
  console.log('Message from worker:', event.data);
};

// worker.js
self.onmessage = function(event) {
  console.log('Message from main script:', event.data);
  self.postMessage('Hello, main script');
};
```

## Resources

- [MDN HTML5](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/HTML5)
- [W3Schools HTML5 Tutorial](https://www.w3schools.com/html/html5_intro.asp)
- [HTML5 Doctor](http://html5doctor.com/)
- [HTML5 Canvas Cheat Sheet](https://htmlcheatsheet.com/canvas/)

## Summary Table

| Feature                | Syntax Example                                                                 | Description                                                      |
|------------------------|--------------------------------------------------------------------------------|------------------------------------------------------------------|
| Semantic Elements      | `<header>`, `<nav>`, `<section>`, `<article>`, `<aside>`, `<footer>`           | New elements that provide better structure and meaning           |
| New Input Types        | `<input type="email">`, `<input type="date">`, `<input type="color">`          | New input types for forms                                        |
| New Form Attributes    | `autocomplete`, `autofocus`, `placeholder`, `required`, `pattern`, `min`, `max`, `step` | New attributes to enhance form functionality                     |
| Audio Element          | `<audio controls> <source src="audio-file.mp3" type="audio/mpeg"> </audio>`     | Embedding audio content                                          |
| Video Element          | `<video controls> <source src="video-file.mp4" type="video/mp4"> </video>`      | Embedding video content                                          |
| Canvas API             | `<canvas id="myCanvas" width="500" height="400"> </canvas>`                    | Drawing graphics via JavaScript                                  |
| Local Storage          | `localStorage.setItem('key', 'value')`, `localStorage.getItem('key')`          | Storing data with no expiration date                             |
| Session Storage        | `sessionStorage.setItem('key', 'value')`, `sessionStorage.getItem('key')`      | Storing data for the duration of the page session                |
| Geolocation            | `navigator.geolocation.getCurrentPosition(success, error)`                     | Retrieving the geographical location of the user                 |
| Web Workers            | `const worker = new Worker('worker.js')`, `worker.postMessage('message')`      | Running scripts in background threads                            |

