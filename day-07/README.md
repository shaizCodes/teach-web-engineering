# Day 07: Flexbox Layouts and Card Components

## Table of Contents

- [Overview](#overview)
- [Key Topics & Activities](#key-topics--activities)
  - [Introduction to Flexbox](#introduction-to-flexbox)
  - [Flex Container Properties](#flex-container-properties)
  - [Flex Item Properties](#flex-item-properties)
  - [Building Card-Based Layouts](#building-card-based-layouts)
  - [Practical Flexbox Applications](#practical-flexbox-applications)
- [Assignment](#assignment)
- [Demo](#demo)
- [Reflections](#reflections)
- [References](#references)
- [Footnotes](#footnotes)

## Overview

Today we explored CSS Flexbox, one of the most powerful layout tools in modern CSS. We learned how to create flexible elements using flex containers and items.

## Key Topics & Activities

### Introduction to Flexbox

Flexbox (Flexible Box Layout) is a one-dimensional layout method for arranging items in rows or columns[^1]. It allows items to grow, shrink, and align properly within a container, making responsive design much easier than older layout methods.

Key advantages:

- Simple alignment and distribution of space
- Direction-agnostic layout control
- Works well with responsive design
- Reduces need for complex positioning

### Flex Container Properties

The parent element must have `display: flex` to activate flexbox. Common container properties include:

- **flex-direction**: Controls the main axis direction (`row`, `row-reverse`, `column`, `column-reverse`)
- **justify-content**: Aligns items along the main axis (`flex-start`, `center`, `space-between`, `space-around`, `space-evenly`)
- **align-items**: Aligns items along the cross axis (`flex-start`, `center`, `stretch`)
- **align-content**: Controls spacing between flex lines (when items wrap)
- **flex-wrap**: Allows items to wrap to next line (`wrap`, `nowrap`, `wrap-reverse`)
- **gap**: Creates space between flex items

### Flex Item Properties

Properties applied to child elements within a flex container:

- **flex-grow**: How much the item grows relative to siblings (default: 0)
- **flex-shrink**: How much the item shrinks relative to siblings (default: 1)
- **flex-basis**: The default size of an item before space is distributed
- **flex**: Shorthand for `flex-grow`, `flex-shrink`, and `flex-basis`
- **align-self**: Override `align-items` for a specific item
- **order**: Change visual order of items

### Building Card-Based Layouts

Card-based UI is a popular design pattern. Cards typically contain:

- Title or heading
- Content or description
- Values or metrics
- Optional icons or media
- Call-to-action (buttons or links)

Cards are often displayed in a grid or flex layout, allowing them to be:**responsive**, **readable**, and **organized**.

### Practical Flexbox Applications

Common use cases:

- Navigation bars and menus
- Card layouts and dashboards
- Form layouts
- Hero sections with side-by-side content
- Footers with multiple columns

## Assignment

- [Assignment: Clone the cards](./ASSIGNMENT.md)

## Demo

See `index.html` for a working sample featuring boxes and flexbox.

> ![Editing flexbox properties using built-in Chrome DevTools features](./recordings/Flexbox-in-Chrome-DevTools.gif)
> Using built-in Chrome DevTools flexbox features to change its properties

Open the file in your browser and inspect the CSS to see how flexbox properties are applied.

## Reflections

- How does flexbox simplify responsive design compared to `display: inline-block`?

## References

- [MDN: CSS Flexible Box Layout](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Flexible_Box_Layout)
- [MDN: justify-content](https://developer.mozilla.org/en-US/docs/Web/CSS/justify-content)
- [MDN: align-items](https://developer.mozilla.org/en-US/docs/Web/CSS/align-items)
- [CSS-Tricks: A Complete Guide to Flexbox](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)
- [Flexbox Froggy: Interactive Learning Game](https://flexboxfroggy.com/)

## Footnotes

[^1]: Flexbox is one-dimensional, meaning it lays out items either in a row or column, but not both simultaneously. For two-dimensional layouts, consider CSS Grid.

---

[Back to Main README](../README.md)
