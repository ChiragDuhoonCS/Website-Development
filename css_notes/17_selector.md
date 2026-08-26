# Video 16 — CSS Selectors

## 1. What is a CSS Selector?

A **selector** tells CSS **which HTML elements to style**.

Basic syntax:

```css
selector {
    property: value;
}
```

Example:

```css
p {
    color: red;
}
```

This selects all `<p>` elements and makes their text red.

---

# 2. Element Selector

Selects elements using their **HTML tag name**.

```css
p {
    color: red;
}
```

This applies to **all `<p>` elements**.

Example:

```html
<p>Hello</p>
<p>World</p>
```

Both become red.

### Tip 💡

Use element selectors when you want the same style applied to **every element of that type**.

---

# 3. ID Selector

Selects an element using its `id`.

HTML:

```html
<p id="first">Hello</p>
```

CSS:

```css
#first {
    color: blue;
}
```

### Syntax

```css
#id-name {
    property: value;
}
```

`#` identifies an **ID selector**.

### Tip 💡

An `id` should normally be **unique** on a page.

---

# 4. Class Selector

Selects elements using their `class`.

HTML:

```html
<p class="red">Hello</p>
<p class="red">World</p>
```

CSS:

```css
.red {
    color: red;
}
```

Both paragraphs become red.

### Syntax

```css
.class-name {
    property: value;
}
```

`.` identifies a **class selector**.

### Tip 💡

Use classes when the **same styling needs to be reused** on multiple elements.

---

# 5. Universal Selector

The universal selector `*` selects **all elements**.

```css
* {
    margin: 0;
    padding: 0;
}
```

This applies the rule to every element.

### Syntax

```css
* {
    property: value;
}
```

---

# 6. Grouping Selector

Multiple selectors can be grouped using a comma.

```css
h1, h2, p {
    color: blue;
}
```

This applies the same styling to:

```text
h1
h2
p
```

### Without grouping

You would have to write:

```css
h1 {
    color: blue;
}

h2 {
    color: blue;
}

p {
    color: blue;
}
```

Grouping avoids repetition.

### Tip 💡

If different selectors have the **same CSS rule**, group them with `,`.

---

# 7. Element + Class Selector

You can combine an element and class:

```css
p.red {
    color: red;
}
```

This specifically targets:

```html
<p class="red">Hello</p>
```

It does **not** target:

```html
<div class="red">Hello</div>
```

because the selector requires both:

```text
p + .red
```

---

# 8. Element + ID Selector

Similarly:

```css
p#first {
    color: blue;
}
```

Targets a `<p>` having `id="first"`.

```html
<p id="first">Hello</p>
```

---

# 9. Descendant Selector

A space between selectors means **an element inside another element**.

```css
div p {
    color: red;
}
```

This selects `<p>` elements that are inside a `<div>`.

Example:

```html
<div>
    <p>Hello</p>
</div>
```

The `<p>` becomes red.

But:

```html
<p>Hello</p>
```

outside the `<div>` is not selected.

### Remember

```text
div p
│   │
│   └── descendant
└────── parent/ancestor
```

---

# 10. Child Selector

The `>` symbol selects **direct children**.

```css
div > p {
    color: red;
}
```

Example:

```html
<div>
    <p>Hello</p>
</div>
```

Here `<p>` is a direct child of `<div>`.

But in:

```html
<div>
    <section>
        <p>Hello</p>
    </section>
</div>
```

`p` is **not** a direct child of `div`, so `div > p` doesn't select it.

---

# 11. Attribute Selector

You can select elements based on their attributes.

Example:

```css
input[type="text"] {
    border: 1px solid black;
}
```

This targets:

```html
<input type="text">
```

### General syntax

```css
[attribute="value"] {
    property: value;
}
```

---

# 12. Selector Summary

| Selector        | Meaning                            |
| --------------- | ---------------------------------- |
| `p`             | All `<p>` elements                 |
| `#id`           | Element with that ID               |
| `.class`        | Elements with that class           |
| `*`             | All elements                       |
| `h1, p`         | Both selectors                     |
| `p.red`         | `<p>` with class `red`             |
| `p#first`       | `<p>` with ID `first`              |
| `div p`         | `<p>` anywhere inside `<div>`      |
| `div > p`       | Direct `<p>` child of `<div>`      |
| `[type="text"]` | Elements with that attribute/value |

---

# ⭐ Tips

* `#` → **ID**
* `.` → **Class**
* `*` → **Everything**
* `,` → **Group**
* Space → **Descendant**
* `>` → **Direct child**
* `[]` → **Attribute**

### Easy memory trick

```text
#id       → one specific identity
.class    → reusable group
*         → everyone
A B       → B inside A
A > B     → B directly inside A
```

---

# ⚡ Quick Revision

```css
p { }                 /* Element */
#box { }              /* ID */
.red { }              /* Class */
* { }                 /* Universal */
h1, p { }             /* Grouping */
p.red { }             /* Element + class */
p#box { }             /* Element + ID */
div p { }             /* Descendant */
div > p { }           /* Direct child */
input[type="text"] { }/* Attribute */
```

**Most important:**
A CSS selector answers one question:

> **“Which HTML element(s) should this CSS rule apply to?”**
