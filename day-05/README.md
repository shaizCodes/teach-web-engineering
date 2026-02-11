# Day 05: CSS Units, BEM, and Emmet

## Table of Contents

- [Overview](#overview)
- [Key Topics & Activities](#key-topics--activities)
  - [CSS Units](#css-units)
  - [BEM (Block Element Modifier)](#bem-block-element-modifier)
  - [Emmet Shortcuts Demonstration](#emmet-shortcuts-demonstration)
- [Assignment](#assignment)
- [Demo](#demo)
- [Reflections](#reflections)

## Overview

Today we covered CSS units and BEM (Block, Element, Modifier) CSS class naming conventions, and used Emmet to speed up markup creation. The session combined short explanations with live hands-on problem-solving demonstration targeting `inline-block` components, relative **CSS units** and `calc()`.

---

## Key Topics & Activities

### CSS Units

- **%**: Relative to the parent element size (useful for fluid layouts).
- **em**: Relative to the parent element's font size (good for component-relative sizing).
- **rem**: Relative to the root (`html`) font size (good for consistent typographic scale).
- **vh**: Relative to 1% of the viewport height (useful for full-height sections).
- **vw**: Relative to 1% of the viewport width (useful for responsive widths).
- **px**: Absolute unit, dependent on device resolution (use for precise control when necessary).

  > ![CSS units demonstration with Chrome DevTools edits](./recordings/editing-font-size-in-Chrome-DevTools-to-understand-CSS-em-and-rem-units.gif)
  >
  > In the attached clip, the footer and header elements have been defined with different font-sizes, while their children are using `em` units. Zooming in and out affects these elements, however, the `vw`.

### BEM (Block Element Modifier)

- **Block**: Standalone component name (e.g., `card`).
- **Element**: Child of a block, written as `block__element` (e.g., `card__title`).
- **Modifier**: Variant of a block or element, written as `block--modifier` or `block__element--modifier` (e.g., `card--featured`, `card__title--large`).

Example HTML:

```html
<div class="card card--featured">
  <h2 class="card__title card__title--large">Card Title</h2>
  <p class="card__body">Card body content...</p>
  <button class="card__btn card__btn--primary">Action</button>
</div>
```

### Emmet Shortcuts Demonstration

- Used Emmet abbreviations to scaffold HTML quickly for prototyping and assignments.
- Common Emmet shortcuts and when to use them:
  - **Child (`>`)**: create a direct child. Use when you want a parent/child relationship.

    ```emmet
    ul>li*3
    ```

    ```html
    <ul>
        <li></li>
        <li></li>
        <li></li>
    </ul>
    ```

  - **Sibling (`+`)**: create adjacent sibling elements. Use for lists of sibling blocks.

    ```emmet
    h1+p+div
    ```

    ```html
    <h1></h1>
    <p></p>
    <div></div>
    ```

  - **Grouping `()`**: group sub-expressions for multiplication or combining with siblings/children.

    ```emmet
    div>(header>ul>li*2)+footer
    ```

    ```html
    <div>
        <header>
            <ul>
                <li></li>
                <li></li>
            </ul>
        </header>
        <footer></footer>
    </div>
    ```

  - **Multiplication (`*`)**: repeat elements. Use to quickly generate multiple similar nodes.

    ```emmet
    li*5
    ```

    ```html
    <li></li>
    <li></li>
    <li></li>
    <li></li>
    <li></li>
    ```

  - **Class (`.`) and ID (`#`)**: add classes or ids quickly.

    ```emmet
    div#card-1.card.card--featured
    ```

    ```html
    <div id="card-1" class="card card--featured"></div>
    ```

  - **Text (`{...}`)**: set element text content.

    ```emmet
    button{Press the button}
    ```

    ```html
    <button>Press the button</button>
    ```

  - **Numbering (`$`)**: auto-number repeated elements when combined with `*`. `@` can be used to change numbering start value.

    ```emmet
    div{$}*3+div.start-changed{$@4}*2
    ```

    ```html
    <div>1</div>
    <div>2</div>
    <div>3</div>
    <div class="start-changed">4</div>
    <div class="start-changed">5</div>
    ```

  - **Attributes (`[attr=value]`)**: add attributes to elements inline.

    ```emmet
    a[href="/"]{Home}+a[href="/about"]{About}+a[href="/contact"]{Contact}
    ```

    ```html
    <a href="/">Home</a><a href="/about">About</a><a href="/contact">Contact</a>
    ```

---

## Assignment

- [Assignment 01: CSS Units & Layout](./ASSIGNMENT.md)

---

## Demo

- A runnable demo showing the units is available: [index.html](./index.html)

Open the file in a browser and resize the viewport to observe differences between `em`, `rem`, `vh`, `vw`, `%` and `px` in action.

---

## Reflections

- Learners found value in seeing how `em` vs `rem` behave differently when parent sizes change.
- BEM clarified component structure and made styling more predictable.
- Emmet saved time and reduced typing during the live problem-solving portion.

---

[Back to Main README](../README.md)
