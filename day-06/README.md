# Day 06: Accessibility in DevTools and Formatting Tags

## Table of Contents

- [Overview](#overview)
- [Key Topics & Activities](#key-topics--activities)
  - [Chrome DevTools Accessibility Panel](#chrome-devtools-accessibility-panel)
  - [Semantic Formatting Tags](#semantic-formatting-tags)
  - [Presentational Formatting Tags](#presentational-formatting-tags)
  - [DevTools Practice Steps](#devtools-practice-steps)
  - [Assignment](#assignment)
- [Demo](#demo)
- [Reflections](#reflections)
- [References](#references)
- [Footnotes](#footnotes)

## Overview

Today we focused on how Chrome DevTools exposes accessibility information, and how formatting tags change meaning for screen readers. We compared semantic formatting tags that add meaning with presentational tags that only change appearance.

## Key Topics & Activities

### Chrome DevTools Accessibility Panel

- How the Accessibility tree[^1] reflects semantic meaning.
- How to inspect accessible name, role, and properties for elements.
- Common properties to look for: accessible **name**, **role**, **description**, **state** (`disabled`/`expanded`/`pressed`), **value**, and **relationships** (like `aria-labelledby`).

### Semantic Formatting Tags

- **strong**: importance
- **em**: emphasis
- **s**: no longer relevant or accurate (semantic strikethrough)
- **del**: deleted text[^2]
- **ins**: inserted text
- **sub**: subscript
- **sup**: superscript

### Presentational Formatting Tags

- **b**: bold style
- **i**: italic style
- **u**: underline
- **small**: smaller font
- **big**: larger font

> [!CAUTION]
> `<big>` is obsolete in HTML5. Avoid it and use CSS (for example, `font-size`) so presentation stays in styles instead of markup.

### DevTools Practice Steps

1. Open index.html in Chrome.
2. Right click an example and choose Inspect.
3. Open the Accessibility panel in DevTools.
4. Compare how semantic vs presentational tags are represented.

## Accessibility Properties (More Detail)

When you select an element in Chrome DevTools and open the Accessibility panel, you will typically see these properties:

- **Role**: what the element is (button, link, heading, textbox). Native elements set this automatically; ARIA can override it.
- **Name**: the accessible label read by screen readers. This can come from visible text, `aria-label`, or `aria-labelledby`.
- **Description**: extra context, often from `aria-describedby` or a title attribute.
- **State**: flags like `disabled`, `pressed`, `expanded`, `checked`, or `selected`.
- **Value**: the current value for inputs (for example, a textbox value).
- **Relationships**: links to other elements that label or describe the element.

### Example: Button

```html
<button id="save">Save</button>
```

Expected accessibility properties:

- Role: `button`
- Name: `Save`
- State: not disabled

### Example: Icon-only Button (needs an accessible name)

```html
<button aria-label="Close dialog">
  <svg aria-hidden="true" viewBox="0 0 24 24">
    <!-- icon paths -->
  </svg>
</button>
```

Expected accessibility properties:

- Role: `button`
- Name: `Close dialog`
- State: not disabled

### Example: Toggle Button (pressed state)

```html
<button aria-pressed="true">Play</button>
```

Expected accessibility properties:

- Role: `button`
- Name: `Play`
- State: pressed

### Example: Button Labeled by Another Element

```html
<span id="add-label">Add to cart</span>
<button aria-labelledby="add-label">
  +
</button>
```

Expected accessibility properties:

- Role: `button`
- Name: `Add to cart`
- Relationships: `aria-labelledby` points to `#add-label`

> [!TIP]
> In a future class we will cover accessibility in more detail with productive tools and hands-on challenges.

## Assignment

- [Assignment 01: Cards Layout with BEM](./ASSIGNMENTS.md)

## Demo

- A runnable demo for the lesson is available: [index.html](./index.html)

  > ![Chrome DevTools Accessibility panel demo](./recordings/accessibility-in-Chrome-DevTools.gif)
  >
  > This short clip shows the Day 06 page running in the browser while DevTools highlights how the Accessibility tree exposes semantic meaning and accessible names for formatting examples.

> [!TIP]
> Open the file in a browser and use DevTools to compare the Accessibility tree for each example.

## Reflections

- Learners observed that meaningful tags announce changes more clearly than visual-only tags.
- Comparing pairs like `strong` vs `b` made the difference between semantics and styling easy to understand.
- We clarified that `s` is semantic for content that is no longer relevant, while `del` marks document edits.

## References

- MDN: [`<s>`: The Strikethrough element](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/s)
- MDN: [`<del>`: The Deleted Text element](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/del)
- MDN: [Accessibility tree glossary](https://developer.mozilla.org/en-US/docs/Glossary/Accessibility_tree)
- Chrome DevTools: [A deep dive into the full accessibility tree](https://developer.chrome.com/blog/full-accessibility-tree)

## Footnotes

[^1]: The Accessibility Tree is a subset of the DOM tree that contains objects for every element that needs to be exposed to assistive technology (like screen readers). It provides accessible `name`, `description`, `role`, and `state`, plus possible actions.
[^2]: While `del` and `s` look visually similar (strikethrough), `del` specifically implies a versioning change in the document, often used in conjunction with `ins`.

> [!NOTE]
> HTML 5 introduced semantic tags will be covered in coming days.

---

[Back to Main README](../README.md)
