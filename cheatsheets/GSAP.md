
# GSAP Animation Cheat Sheet

## Table of Contents

- [Introduction](#introduction)
- [Installation](#installation)
- [Basic Usage](#basic-usage)
- [Core Methods](#core-methods)
- [Easing](#easing)
- [Plugins](#plugins)
- [Tips and Tricks](#tips-and-tricks)
- [Resources](#resources)
- [Summary Table](#summary-table)

## Introduction

GSAP (GreenSock Animation Platform) is a robust JavaScript library for high-performance HTML5 animations. It's used by major companies and creative developers around the world to create stunning, interactive animations.

## Installation

You can include GSAP in your project via a CDN or by installing it with npm.

### CDN

```html
<script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.10.4/gsap.min.js"></script>
```

### npm

```sh
npm install gsap
```

## Basic Usage

To animate an element, use the `gsap.to`, `gsap.from`, or `gsap.fromTo` methods.

### Example

```html
<div class="box"></div>

<style>
  .box {
    width: 100px;
    height: 100px;
    background-color: red;
  }
</style>

<script>
  gsap.to(".box", { x: 100, duration: 2 });
</script>
```

## Core Methods

### Tweening

- `gsap.to(target, vars)`: Animate from the current state to the specified state.
- `gsap.from(target, vars)`: Animate from the specified state to the current state.
- `gsap.fromTo(target, fromVars, toVars)`: Specify both the start and end states.

#### Example

```js
// gsap.to
gsap.to(".box", { x: 100, duration: 2 });

// gsap.from
gsap.from(".box", { y: 50, opacity: 0, duration: 1 });

// gsap.fromTo
gsap.fromTo(".box", { x: 0, y: 0 }, { x: 100, y: 50, duration: 1 });
```

### Timelines

Timelines allow you to create sequenced animations.

```js
let tl = gsap.timeline();

tl.to(".box", { x: 100, duration: 1 })
  .to(".box", { y: 100, duration: 1 })
  .to(".box", { rotation: 360, duration: 1 });
```

## Easing

Easing functions control the acceleration of the animation.

```js
gsap.to(".box", { x: 100, duration: 2, ease: "power1.inOut" });
```

Common eases:
- `power1`, `power2`, `power3`, `power4`
- `elastic`
- `bounce`
- `back`
- `sine`
- `expo`
- `circ`

## Plugins

GSAP offers various plugins to extend its capabilities.

### Common Plugins

- `ScrollTrigger`: Create scroll-based animations.
- `MotionPathPlugin`: Animate along a path.
- `Draggable`: Make elements draggable.

### Example: ScrollTrigger

```html
<script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.10.4/ScrollTrigger.min.js"></script>

<script>
  gsap.registerPlugin(ScrollTrigger);

  gsap.to(".box", {
    scrollTrigger: {
      trigger: ".box",
      start: "top 80%",
      end: "top 30%",
      scrub: true,
    },
    x: 500,
  });
</script>
```

## Tips and Tricks

### Example: Responsive Animation

```js
gsap.matchMedia().add("(min-width: 768px)", () => {
  gsap.to(".box", { x: 100, duration: 2 });
});
```

## Resources

- [GSAP Documentation](https://greensock.com/docs/)
- [GSAP Getting Started](https://greensock.com/get-started/)
- [GSAP Plugins](https://greensock.com/plugins/)
- [GSAP Forum](https://greensock.com/forums/)

## Summary Table

| Feature          | Syntax Example                               | Description                                            |
|------------------|----------------------------------------------|--------------------------------------------------------|
| Basic Animation  | \`gsap.to(".box", { x: 100, duration: 2 })\`   | Animates an element to the specified properties        |
| From Animation   | \`gsap.from(".box", { opacity: 0, duration: 1 })\` | Animates an element from the specified properties      |
| FromTo Animation | \`gsap.fromTo(".box", { x: 0 }, { x: 100 })\`  | Animates an element from and to the specified properties |
| Timelines        | \`let tl = gsap.timeline(); tl.to(...).to(...);\` | Sequences multiple animations                          |
| Easing           | \`ease: "power1.inOut"\`                       | Applies easing functions to animations                 |
| ScrollTrigger    | \`ScrollTrigger.create({ trigger: "...", ... })\` | Creates scroll-based animations                        |
| MotionPathPlugin | \`MotionPathPlugin\`                           | Animates elements along a path                         |
| Draggable        | \`Draggable.create(".box", { ... })\`          | Makes elements draggable                               |
| Responsive       | \`gsap.matchMedia().add("(min-width: ...)", () => { ... })\` | Creates responsive animations using matchMedia        |
| Performance      | Use \`will-change\` CSS property for smoother animations.                              |
| Debugging        | Use \`console.log(gsap.globalTimeline)\` to inspect the global timeline.               |
| Using Functions  | Use functions to dynamically set properties.                                         |
| Stagger          | Use \`stagger\` property to create staggered animations for multiple elements.         |
| Labels           | Use labels in timelines to easily manage complex sequences.                          |
| Repeats          | Use \`repeat\` and \`yoyo\` properties for repeating animations.                         |

