Yes — **Lecture 31 is CSS Media Queries**, not transforms. Here are the corrected notes.

# CSS Media Queries — Tutorial #31

## 1. What are Media Queries?

**Media queries** are used to apply different CSS styles depending on the **device/screen conditions**.

Main use → **Responsive Web Design**.

Example:

```css
@media only screen and (max-width: 600px) {
    body {
        background-color: lightblue;
    }
}
```

This style applies when the screen width is **600px or less**.

---

## 2. Basic Syntax

```css
@media condition {
    /* CSS */
}
```

More commonly:

```css
@media only screen and (max-width: 600px) {
    /* CSS */
}
```

### Parts

```text
@media
   ↓
media query

only screen
   ↓
type of media

(max-width: 600px)
   ↓
condition

{ CSS }
   ↓
styles to apply
```

---

## 3. `max-width`

`max-width` applies CSS when the viewport is **at or below** the specified width.

```css
@media only screen and (max-width: 600px) {
    .box {
        background-color: red;
    }
}
```

```text
Width ≤ 600px
     ↓
CSS applies
```

---

## 4. `min-width`

`min-width` applies CSS when the viewport is **at or above** the specified width.

```css
@media only screen and (min-width: 600px) {
    .box {
        background-color: green;
    }
}
```

```text
Width ≥ 600px
     ↓
CSS applies
```

### 🧠 Remember

```text
max-width → up to this size
min-width → from this size
```

---

## 5. Responsive Design Example

Normal CSS:

```css
.container {
    display: flex;
}
```

For smaller screens:

```css
@media only screen and (max-width: 600px) {
    .container {
        flex-direction: column;
    }
}
```

So:

```text
Large screen → items side-by-side

Small screen
     ↓
items stacked vertically
```

This is the basic idea behind responsive websites.

---

## 6. Media Types

Common media types include:

```text
screen
print
```

Example:

```css
@media print {
    body {
        color: black;
    }
}
```

This CSS applies when the document is printed.

For normal displays:

```css
@media screen {
    /* styles */
}
```

---

## 7. `only`

Example:

```css
@media only screen and (max-width: 600px) {
    ...
}
```

`only` restricts the query to the specified media type.

For modern web development, you will commonly see:

```css
@media screen and (max-width: 600px) {
    ...
}
```

or simply:

```css
@media (max-width: 600px) {
    ...
}
```

---

## 8. `and`

`and` allows you to combine multiple conditions.

```css
@media screen and (max-width: 600px) {
    ...
}
```

Both conditions must match:

```text
screen
  AND
width ≤ 600px
```

You can combine more conditions:

```css
@media screen and (min-width: 400px) and (max-width: 600px) {
    ...
}
```

This applies between **400px and 600px**.

---

## 9. Common Breakpoint Idea

You can create different styles for different screen sizes.

```css
/* Desktop */
.box {
    width: 50%;
}

/* Smaller screens */
@media (max-width: 600px) {
    .box {
        width: 100%;
    }
}
```

Result:

```text
Large screen → 50% width
Small screen → 100% width
```

---

## ⭐ Tips

* Media queries are mainly used for **responsive design**.
* `max-width` → styles apply **up to** that width.
* `min-width` → styles apply **from** that width.
* Don't assume every device has a fixed width; use breakpoints based on when your layout actually needs to change.
* Media queries can modify existing CSS properties inside the query.
* You can use media queries with **Flexbox, Grid, fonts, spacing, display, etc.**

### Very important pattern:

```css
@media (max-width: 600px) {
    /* mobile/smaller-screen styles */
}
```

---

# ⚡ Quick Revision

```css
/* Maximum width */
@media (max-width: 600px) {
    .box {
        width: 100%;
    }
}
```

```css
/* Minimum width */
@media (min-width: 600px) {
    .box {
        width: 50%;
    }
}
```

```css
/* Range */
@media (min-width: 400px) and (max-width: 600px) {
    .box {
        width: 80%;
    }
}
```

### 🧠 Remember

**Media Query = condition-based CSS**

```text
Screen condition
      ↓
Does condition match?
   ↙       ↘
 YES       NO
  ↓         ↓
Apply CSS   Ignore CSS
```
