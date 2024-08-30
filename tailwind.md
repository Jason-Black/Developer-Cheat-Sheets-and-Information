# GSAP Animation Cheat Sheet

## Table of Contents

- [Introduction](#introduction)
- [Installation](#installation)
- [Basic Usage](#basic-usage)
- [Responsive Design](#responsive-design)
  - [Using Media Tags](#using-media-tags)
  - [Tailwind Responsive Design](#tailwind-responsive-design)
- [Core Concepts](#core-concepts)
- [Utility Classes](#utility-classes)
- [Tips and Tricks](#tips-and-tricks)
- [Advanced Features](#advanced-features)
  - [Animating with Tailwind CSS](#animating-with-tailwind-css)
  - [Transition Utilities](#transition-utilities)
  - [Advanced Customization](#advanced-customization)
- [Resources](#resources)
- [Summary Table](#summary-table)

## Introduction

Tailwind CSS is a utility-first CSS framework that provides low-level utility classes to build custom designs without writing CSS. It is highly customizable and promotes a responsive, mobile-first design philosophy.

## Installation

You can include Tailwind CSS in your project via a CDN or by installing it with npm.

### CDN

```html
<link href="https://cdn.jsdelivr.net/npm/tailwindcss@2.2.19/dist/tailwind.min.css" rel="stylesheet">
```

### npm

```sh
npm install tailwindcss
```

### Basic Configuration

```sh
npx tailwindcss init
```

This command generates a `tailwind.config.js` file in your project.

## Basic Usage

To use Tailwind CSS, apply utility classes directly to your HTML elements.

### Example

```html
<div class="bg-blue-500 text-white p-4 rounded-lg">
  Hello, Tailwind CSS!
</div>
```

## Responsive Design

# Best Video I have found on Responsive design

<a href="https://www.youtube.com/watch?v=rbSPe1tJowY" target="_blank">
  <img src="https://img.youtube.com/vi/rbSPe1tJowY/maxresdefault.jpg" alt="Watch the video" width="300"/>
</a>



- HTML CODE
```html <!-- You can literally design anything with GRID -->

<!-- You can literally design anything with GRID -->

<!-- Equal Sections -->

<!-- Most common - 2x1 on md screens and vertical align on phone -->

<!-- <div class="grid gap-4 sm:grid-cols-2 m-4">
  <div class="bg-blue-400 min-h-[100px] rounded-lg shadow"></div>
    <div class="bg-red-400 min-h-[100px] rounded-lg shadow"></div>
    

</div> -->

<!-- 3 pieces of content that goes 3x1 on md screens and vertical align on phone -->

<!-- <div class="grid gap-4 sm:grid-cols-3 m-4">
  <div class="bg-blue-400 min-h-[100px] rounded-lg shadow"></div>
    <div class="bg-red-400 min-h-[100px] rounded-lg shadow"></div>
      <div class="bg-green-400 min-h-[100px] rounded-lg shadow"></div>
</div> -->

<!-- 4 pieces of content that gose 2x2 on md screens and vertical aligh on phone -->

<!-- <div class="grid gap-4 sm:grid-cols-2 m-4">
  <div class="bg-blue-400 min-h-[100px] rounded-lg shadow"></div>
    <div class="bg-red-400 min-h-[100px] rounded-lg shadow"></div>
      <div class="bg-green-400 min-h-[100px] rounded-lg shadow"></div>
      <div class="bg-orange-400 min-h-[100px] rounded-lg shadow"></div>
</div> -->

<!-- Non-Equal Sections -->


<!-- 2 pieces of content that goes 20/80 2x1 on med screens and vertical align on phone -->

<!-- <div class="grid gap-4 sm:grid-cols-12 grid-col-2 m-4">
  <div class="bg-blue-400 min-h-[100px] rounded-lg shadow sm:col-span-2"></div>
    <div class="bg-red-400 min-h-[100px] rounded-lg shadow sm:col-span-10"></div>
   
</div> -->

<!-- This also works??? 2 pieces of content that goes 20/80 2x1 on med screens and vertical align on phone -->

<!-- <div class="grid gap-4 sm:grid-cols-12  m-4">
  <div class="bg-blue-400 min-h-[100px] rounded-lg shadow sm:col-span-2"></div>
    <div class="bg-red-400 min-h-[100px] rounded-lg shadow sm:col-span-10"></div>
   
</div> -->

<!-- This also works LOL??? 2 pieces of content that goes 20/80 2x1 on med screens and vertical align on phone -->

<!-- <div class="grid gap-4 sm:grid-cols-12 grid-cols-1 m-4">
  <div class="bg-blue-400 min-h-[100px] rounded-lg shadow sm:col-span-2"></div>
    <div class="bg-red-400 min-h-[100px] rounded-lg shadow sm:col-span-10"></div>
   
</div> -->

<!-- 3x pieces of content that 'dissappears the colums' as you get smaller and fills up the screen with main content (kinda clunky) -->

<!-- <div class="m-4 grid gap-4 sm:grid-cols-12">
  <div class="bg-blue-400 min-h-[100px] sm:col-span-2 rounded-lg shadow "></div>
    <div class="bg-red-400 min-h-[100px] sm:col-span-8 rounded-lg shadow "></div>
        <div class="bg-purple-400 min-h-[100px] sm:col-span-2 rounded-lg shadow "></div>
   
</div> -->

<!-- 3x pieces of content that 'dissappears the colums' as you get smaller and fills up the screen with main content (but where do you put that content later?) This hides the left and right cols on phone, and only displays middle, and on larger screens displays 3x1 10%-80%-10% -->

<div class="m-4 grid gap-4 sm:grid-cols-12">
  <div class="bg-blue-400 min-h-[100px] sm:col-span-2 rounded-lg shadow sm:block hidden "></div>
    <div class="bg-red-400 min-h-[100px] sm:col-span-8 rounded-lg shadow "></div>
        <div class="bg-purple-400 min-h-[100px] sm:col-span-2 rounded-lg shadow sm:block hidden "></div>
   
</div>

<!-- 3x pieces of content that 'dissappears the colums' as you get smaller and fills up the screen with main content (but where do you put that content later?) This hides the left and right cols on phone, and only displays middle, and on larger screens displays 3x1 10%-80%-10% this one changes which box is displayed on phone-->

<div class="m-4 grid gap-4 sm:grid-cols-12">
  <div class="bg-blue-400 min-h-[100px] sm:col-span-2 rounded-lg shadow sm:block hidden "></div>
    <div class="bg-red-400 min-h-[100px] sm:col-span-8 rounded-lg shadow sm:block hidden "></div>
        <div class="bg-purple-400 min-h-[100px] sm:col-span-2 rounded-lg shadow  "></div>
   
</div>
```


Responsive design ensures that your web application looks good on all devices, from mobile phones to desktop computers. It involves using flexible layouts, media queries, and responsive units.

### Using Media Tags

Media queries are used to apply different styles for different devices or screen sizes.

#### Example

```css
@media (min-width: 640px) {
  .example {
    background-color: blue;
  }
}

@media (min-width: 768px) {
  .example {
    background-color: green;
  }
}

@media (min-width: 1024px) {
  .example {
    background-color: red;
  }
}
```

### Tailwind Responsive Design

Tailwind CSS makes responsive design easy with its built-in responsive utilities. You can prefix any utility class with a breakpoint to apply it only on specific screen sizes.

#### Example

```html
<div class="bg-blue-500 md:bg-green-500 lg:bg-red-500 p-4 rounded-lg">
  Responsive Colors
</div>
```

#### Breakpoints

- `sm` - 640px
- `md` - 768px
- `lg` - 1024px
- `xl` - 1280px
- `2xl` - 1536px

## Core Concepts

- **Utility-First**: Use utility classes to build your design directly in your HTML.
- **Responsive Design**: Tailwind's responsive utilities make it easy to create responsive designs.
- **Customization**: Tailwind is highly customizable via the `tailwind.config.js` file.

## Utility Classes

### Spacing

```html
<div class="m-4 p-4">
  Margin and Padding
</div>
```

### Colors

```html
<div class="bg-blue-500 text-white">
  Background and Text Color
</div>
```

### Flexbox

```html
<div class="flex items-center justify-center">
  Flexbox Layout
</div>
```

### Grid

```html
<div class="grid grid-cols-3 gap-4">
  <div>1</div>
  <div>2</div>
  <div>3</div>
</div>
```

## Tips and Tricks

| Tip                | Description                                                                 |
|--------------------|-----------------------------------------------------------------------------|
| Use Responsive Utilities | Apply classes conditionally based on screen size.                      |
| Customize with Config | Use `tailwind.config.js` to customize your design system.                 |
| Purge Unused CSS   | Use Tailwind's purge feature to remove unused styles in production builds.  |
| Combine Classes    | Combine utility classes to create complex designs.                          |
| Dark Mode          | Enable dark mode with the `dark` variant.                                    |
| Arbitrary Values   | Use square brackets for arbitrary values (e.g., `w-[32rem]`).                |

### Example: Customizing Config

```js
// tailwind.config.js
module.exports = {
  purge: ['./src/**/*.{js,jsx,ts,tsx}', './public/index.html'],
  darkMode: 'media', // or 'class'
  theme: {
    extend: {
      colors: {
        'custom-blue': '#1fb6ff',
      },
    },
  },
  variants: {
    extend: {},
  },
  plugins: [],
};
```

## Advanced Features

### Animating with Tailwind CSS

Tailwind CSS provides utility classes for adding animations and transitions to your elements. You can control the duration, delay, and other properties of animations.

#### Example

```html
<div class="transition ease-in-out duration-500 transform hover:scale-105">
  Hover to Scale
</div>
```

### Transition Utilities

Tailwind CSS includes a set of utilities for controlling the transition properties of elements. These utilities can be used to add smooth animations.

#### Example

```html
<div class="transition duration-300 ease-in-out bg-blue-500 hover:bg-blue-700">
  Hover to Change Color
</div>
```

#### Transition Properties

- `transition` - Applies transition to all properties
- `duration-{time}` - Specifies the duration of the transition (e.g., `duration-300`)
- `ease-{timing}` - Specifies the timing function (e.g., `ease-in-out`)
- `delay-{time}` - Specifies the delay before the transition starts (e.g., `delay-150`)

### Advanced Customization

Tailwind CSS can be deeply customized using the configuration file. You can extend the default theme, add new utilities, and configure variants.

#### Example: Extending the Theme

```js
// tailwind.config.js
module.exports = {
  theme: {
    extend: {
      spacing: {
        '128': '32rem',
      },
      borderRadius: {
        '4xl': '2rem',
      },
    },
  },
};
```

## Resources

- [Tailwind CSS Documentation](https://tailwindcss.com/docs)
- [Tailwind CSS Cheat Sheet](https://nerdcave.com/tailwind-cheat-sheet)
- [Tailwind Toolbox](https://www.tailwindtoolbox.com/)
- [Tailwind UI](https://tailwindui.com/)


## Summary Table

| Feature                | Syntax Example                                   | Description                                                    |
|------------------------|--------------------------------------------------|----------------------------------------------------------------|
| Basic Usage            | `<div class="bg-blue-500 p-4">...</div>`         | Basic utility classes for styling elements                     |
| Responsive Design      | `<div class="md:bg-green-500 lg:bg-red-500">...</div>` | Responsive utility classes for different screen sizes          |
| Customizing Config     | `tailwind.config.js`                             | Customize Tailwind's default configuration                     |
| Flexbox                | `<div class="flex items-center justify-center">...</div>` | Use Flexbox utilities for layout                               |
| Grid                   | `<div class="grid grid-cols-3 gap-4">...</div>`  | Use Grid utilities for layout                                  |
| Colors                 | `<div class="bg-blue-500 text-white">...</div>`  | Utility classes for background and text colors                 |
| Spacing                | `<div class="m-4 p-4">...</div>`                 | Utility classes for margin and padding                         |
| PurgeCSS               | `purge: ['./src/**/*.{js,jsx,ts,tsx}', './public/index.html']` | Remove unused styles in production                             |
| Dark Mode              | `dark:bg-black`                                  | Enable dark mode support                                       |
| Arbitrary Values       | `w-[32rem]`                                      | Use arbitrary values for utilities                             |
| Combining Classes      | `<div class="p-4 bg-blue-500 text-white">...</div>` | Combine utility classes to create complex designs              |
| Animating              | `<div class="transition duration-500 ease-in-out">...</div>` | Use transition utilities to add animations                     |
| Transition Duration    | `duration-500`                                   | Control the duration of transitions                            |
| Transition Timing      | `ease-in-out`                                    | Control the timing function of transitions                     |
| Transition Delay       | `delay-150`                                      | Add a delay before the transition starts                       |
| Extending Theme        | `extend: { spacing: { '128': '32rem' } }`        | Extend the default theme with custom values                    |
