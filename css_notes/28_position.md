# Video 28 — CSS Position Property

This lecture introduces the **CSS `position` property**, which controls how an element is positioned in the webpage.

---

## 1. `position`

Syntax:

```css
selector {
    position: value;
}
```

Main values:

```text id="p0l6kf"
static
relative
absolute
fixed
sticky
```

---

# 2. `position: static`

`static` is the **default position** of an element.

```css
.box {
    position: static;
}
```

With static positioning, properties like:

```css
top
right
bottom
left
```

do **not** affect the element in the normal way.

---

# 3. `position: relative`

```css
.box {
    position: relative;
    top: 20px;
    left: 30px;
}
```

The element is positioned **relative to its normal position**.

```text
Normal position
      ↓
┌─────────┐
│  Box    │
└─────────┘
      ↘
     moved
```

### Important

The element's **original space is still preserved** in the layout.

### Tip 💡

`relative` is also commonly used as the positioning reference for an absolutely positioned child.

---

# 4. `top`, `right`, `bottom`, `left`

These properties control an element's position when its positioning allows offsets.

Example:

```css
.box {
    position: relative;
    top: 20px;
    left: 30px;
}
```

Meaning:

```text
top: 20px  → move downward
left: 30px → move right
```

Think carefully about the direction:

```text
top: 20px   → ↓
bottom: 20px → ↑
left: 20px  → →
right: 20px → ←
```

---

# 5. `position: absolute`

```css
.box {
    position: absolute;
}
```

An absolutely positioned element is removed from the **normal document flow** and positioned relative to its nearest positioned ancestor (if one exists).

Example:

```css
.parent {
    position: relative;
}

.child {
    position: absolute;
    top: 10px;
    left: 20px;
}
```

Here `.child` is positioned relative to `.parent`.

### Important ⭐

A common pattern is:

```css
.parent {
    position: relative;
}

.child {
    position: absolute;
}
```

This lets you position the child precisely inside the parent.

---

# 6. Absolute Positioning Without a Positioned Parent

If an absolutely positioned element has no suitable positioned ancestor, it is positioned relative to the relevant containing block, commonly the initial containing block/page.

```css
.child {
    position: absolute;
    top: 0;
    right: 0;
}
```

### Tip 💡

If you want an absolute child to stay inside a particular parent, give that parent:

```css
position: relative;
```

---

# 7. `position: fixed`

```css
.box {
    position: fixed;
    right: 20px;
    bottom: 20px;
}
```

A fixed element is positioned relative to the **viewport** and stays in that position while the page scrolls.

Common uses:

* Floating buttons
* Chat buttons
* Fixed navigation bars
* Back-to-top buttons

```text
┌─────────────────────────┐
│                         │
│        PAGE             │
│                         │
│                     ┌───┐
│                     │ ● │ ← fixed
└─────────────────────┴───┘
```

---

# 8. `position: sticky`

`sticky` behaves somewhat like `relative` until a specified scroll threshold is reached, then it sticks within its containing scroll area.

```css
.heading {
    position: sticky;
    top: 0;
}
```

It can be useful for:

* Sticky headers
* Section headings
* Table headings

### Example

```css
header {
    position: sticky;
    top: 0;
}
```

The header sticks to the top when scrolling reaches it.

### Tip 💡

`sticky` generally needs an offset such as:

```css
top: 0;
```

to define where it should stick.

---

# 9. Position Comparison

| Position   | Normal flow?    | Reference                   |
| ---------- | --------------- | --------------------------- |
| `static`   | Yes             | Normal document flow        |
| `relative` | Yes             | Its normal position         |
| `absolute` | No              | Nearest positioned ancestor |
| `fixed`    | No              | Viewport                    |
| `sticky`   | Yes until stuck | Scroll/container context    |

---

# ⭐ Tips

### Easy memory:

```text
static   → normal
relative → move from normal position
absolute → precise positioning inside a positioned parent
fixed    → fixed to viewport
sticky   → sticks while scrolling
```

### Most important pattern:

```css
.parent {
    position: relative;
}

.child {
    position: absolute;
}
```

This is one of the most useful positioning patterns in CSS.

### Remember

`position: absolute` removes the element from normal document flow, while `relative` **keeps its original space**.

---

# ⚡ Quick Revision

```css
/* Default */
.box {
    position: static;
}

/* Relative to normal position */
.box {
    position: relative;
    top: 20px;
    left: 20px;
}

/* Relative to positioned ancestor */
.box {
    position: absolute;
    top: 0;
    right: 0;
}

/* Fixed to viewport */
.box {
    position: fixed;
    bottom: 20px;
    right: 20px;
}

/* Sticks while scrolling */
.box {
    position: sticky;
    top: 0;
}
```

### 🧠 One-line memory

**Static = normal | Relative = shifted | Absolute = positioned independently | Fixed = viewport | Sticky = scroll + stick**
