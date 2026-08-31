# CSS Selectors — Tutorial #35: More on CSS Selectors

## 1. Attribute Selectors

Attribute selectors select elements based on their **attributes**.

### Select elements having an attribute

```css
a[target] {
    color: red;
}
```

Selects `<a>` elements that have a `target` attribute.

Example:

```html
<a target="_blank">Google</a>
<a>Facebook</a>
```

Only the first `<a>` is selected.

---

## 2. Select by Attribute Value

```css
input[type="text"] {
    background-color: yellow;
}
```

Selects only:

```html
<input type="text">
```

and not:

```html
<input type="password">
```

### Syntax

```css
element[attribute="value"] {
    /* CSS */
}
```

---

# 3. Descendant Selector

Selects elements **inside another element**, at any nesting level.

```css
div p {
    color: red;
}
```

This selects every `<p>` inside a `<div>`.

Example:

```html
<div>
    <p>Hello</p>

    <section>
        <p>World</p>
    </section>
</div>
```

Both `<p>` elements are selected.

### Remember

```text
div p
 ↑   ↑
parent descendant
```

The space between selectors means **descendant**.

---

# 4. Child Selector `>`

Selects only the **direct children**.

```css
div > p {
    color: blue;
}
```

Example:

```html
<div>
    <p>Selected</p>

    <section>
        <p>Not selected</p>
    </section>
</div>
```

Only the first `<p>` is a direct child of `<div>`.

### Difference

```css
div p
```

→ any descendant

```css
div > p
```

→ direct child only

---

# 5. Adjacent Sibling Selector `+`

Selects the element **immediately following** another element.

```css
h1 + p {
    color: red;
}
```

Example:

```html
<h1>Heading</h1>
<p>Selected</p>
<p>Not selected</p>
```

Only the first `<p>` is selected because it immediately follows `<h1>`.

```text
h1
 ↓ +
p  ← selected
```

---

# 6. General Sibling Selector `~`

Selects **all matching siblings that come after** an element.

```css
h1 ~ p {
    color: green;
}
```

Example:

```html
<h1>Heading</h1>
<p>Selected</p>
<div>Something</div>
<p>Selected</p>
```

Both `<p>` elements after the `<h1>` are selected.

### `+` vs `~`

```text
h1 + p
→ only immediate next sibling

h1 ~ p
→ all matching following siblings
```

---

# 7. Grouping Selectors

You can apply the same CSS to multiple selectors by separating them with commas.

```css
h1, h2, p {
    color: blue;
}
```

Instead of:

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

### Tip 💡

Grouping avoids unnecessary repetition.

---

# 8. Universal Selector with Other Selectors

The universal selector:

```css
* {
    margin: 0;
    padding: 0;
}
```

selects **all elements**.

It is commonly used for basic CSS resets.

---

# 9. Pseudo-classes

Pseudo-classes select an element based on a **state or condition**.

Example:

```css
a:hover {
    color: red;
}
```

The style applies when the mouse is over the link.

Common pseudo-classes:

```text
:hover
:active
:visited
:focus
:first-child
:last-child
:nth-child()
```

---

# 10. `:first-child`

Selects an element if it is the **first child** of its parent.

```css
p:first-child {
    color: red;
}
```

Example:

```html
<div>
    <p>First</p>
    <p>Second</p>
</div>
```

The first `<p>` is selected.

---

# 11. `:last-child`

Selects the last child.

```css
p:last-child {
    color: red;
}
```

---

# 12. `:nth-child()`

Selects children based on their position.

```css
li:nth-child(2) {
    color: red;
}
```

Selects the **second child**.

You can also use:

```css
li:nth-child(odd) {
    color: red;
}

li:nth-child(even) {
    color: blue;
}
```

Useful for styling alternating rows/items.

---

# 13. Pseudo-elements

Pseudo-elements style a **specific part of an element**.

Common examples:

```text
::before
::after
::first-letter
::first-line
```

Example:

```css
p::first-letter {
    font-size: 30px;
}
```

This styles only the first letter of the paragraph.

---

## ⭐ Important Selector Differences

### Descendant

```css
div p
```

```text
div
 └── anything
      └── p
```

→ Any descendant.

### Child

```css
div > p
```

```text
div
 └── p
```

→ Direct child only.

### Adjacent sibling

```css
h1 + p
```

```text
h1
└── p
```

→ Immediately next sibling.

### General sibling

```css
h1 ~ p
```

```text
h1
├── p
├── div
└── p
```

→ Matching siblings after it.

---

# ⭐ Tips

### Easy memory

```text
space → descendant
>     → direct child
+     → next sibling
~     → all following siblings
,     → group selectors
[]    → attribute
:     → pseudo-class
::    → pseudo-element
```

### Don't confuse:

```css
:hover
```

**Pseudo-class** → state/condition

```css
::before
```

**Pseudo-element** → specific part/inserted content

---

# ⚡ Quick Revision

```css
/* Attribute */
input[type="text"] { }

/* Descendant */
div p { }

/* Direct child */
div > p { }

/* Immediate sibling */
h1 + p { }

/* All following siblings */
h1 ~ p { }

/* Grouping */
h1, h2, p { }

/* Pseudo-class */
a:hover { }

/* First child */
p:first-child { }

/* Nth child */
li:nth-child(2) { }

/* Pseudo-element */
p::first-letter { }
```

### 🧠 One-line memory

**`space` = inside | `>` = direct child | `+` = next | `~` = following | `[]` = attribute | `:` = state | `::` = element part**
