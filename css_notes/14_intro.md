# Video 14 — Introduction to CSS

## 1. What is CSS?

**CSS = Cascading Style Sheets**

CSS is used to **style and design HTML elements**.

```text
HTML       → Structure
CSS        → Styling
JavaScript → Functionality
```

Example:

```html
<h1>Hello World</h1>
```

Without CSS → browser's default appearance.

With CSS:

```css
h1 {
    color: red;
}
```

→ heading becomes red.

---

## 2. Why CSS?

CSS allows us to control:

* Text color
* Background color
* Font
* Font size
* Spacing
* Borders
* Layout
* Overall appearance

Instead of adding styling separately to every HTML element, CSS lets us create **rules** that can apply to many elements.

---

## 3. CSS Syntax

Basic syntax:

```css
selector {
    property: value;
}
```

Example:

```css
div {
    color: red;
    background-color: yellow;
}
```

### Understand the parts

```text
div
 ↓
Selector

color
 ↓
Property

red
 ↓
Value
```

A complete:

```css
color: red;
```

is a **declaration**.

---

## 4. Selector

A **selector** tells CSS which HTML element(s) to style.

Example:

```css
div {
    color: red;
}
```

Here:

```text
div → selector
```

This targets the `<div>` elements.

---

## 5. Property

A **property** specifies what aspect of the element you want to change.

Examples:

```css
color
background-color
font-size
```

Example:

```css
p {
    color: blue;
}
```

Here:

```text
color → property
blue  → value
```

---

## 6. Value

The **value** specifies how the property should be set.

```css
color: red;
```

* `color` → property
* `red` → value

Different properties accept different types of values.

---

## 7. Multiple Declarations

You can apply multiple styles to the same selector:

```css
div {
    color: red;
    background-color: yellow;
    font-size: 20px;
}
```

All three styles apply to the `<div>`.

---

## 8. Multiple Selectors

The same CSS rule can target multiple elements:

```css
div, span {
    color: red;
}
```

Both `<div>` and `<span>` will have red text.

The comma separates the selectors.

---

## 9. CSS with HTML

HTML:

```html
<div>Hello</div>
<span>World</span>
```

CSS:

```css
div {
    color: red;
}

span {
    color: blue;
}
```

Result:

```text
Hello → red
World → blue
```

---

# ⭐ Tips

* **Remember the CSS pattern:** `selector { property: value; }`
* Think of CSS as giving instructions: **“Select this → change this → to this.”**
* Don't memorize properties randomly. Learn them while building small webpages.
* Keep CSS separate from HTML when a project becomes larger; it makes the code easier to manage.
* A semicolon `;` separates declarations:

```css
p {
    color: red;
    font-size: 20px;
}
```

---

# ⚡ Quick Revision

```text
CSS = Cascading Style Sheets

HTML → Structure
CSS  → Style

Syntax:
selector {
    property: value;
}

Selector  → what to style
Property  → what to change
Value     → how to change it
Declaration → property + value

Multiple selectors:
div, span { ... }
```

**Most important:**
`selector → property → value`
