# Video 22 — CSS Sizing Units

## 1. Why CSS Units?

CSS uses **units** to define sizes such as:

* `width`
* `height`
* `margin`
* `padding`
* `font-size`

Example:

```css
.box {
    width: 200px;
    height: 100px;
}
```

Here `px` is the unit.

---

# 2. Pixels (`px`)

`px` is a **fixed CSS unit**.

```css
.box {
    width: 200px;
    height: 100px;
}
```

The size does not directly depend on the size of the parent element.

### Tip 💡

`px` is useful when you need a specific, predictable size.

---

# 3. Percentage (`%`)

Percentage sizes are generally calculated **relative to the containing element**.

```css
.box {
    width: 50%;
}
```

If the parent is `1000px` wide:

```text
50% of 1000px = 500px
```

### Example

```html
<div class="parent">
    <div class="child"></div>
</div>
```

```css
.parent {
    width: 1000px;
}

.child {
    width: 50%;
}
```

The child becomes `500px` wide.

### Tip 💡

`%` is useful for creating **flexible/responsive layouts**.

---

# 4. `em`

`em` is relative to the **font size of the element's context**.

Example:

```css
.parent {
    font-size: 20px;
}

.child {
    font-size: 2em;
}
```

Approximately:

```text
2em = 2 × 20px = 40px
```

`em` can therefore change depending on inherited/contextual font sizes.

### ⚠️ Tip

Nested elements using `em` can compound their sizes, so be careful when nesting.

---

# 5. `rem`

`rem` means **Root EM**.

It is relative to the font size of the **root (`html`) element**.

Example:

```css
html {
    font-size: 16px;
}

.box {
    font-size: 2rem;
}
```

Result:

```text
2rem = 2 × 16px = 32px
```

### `em` vs `rem`

```text
em  → relative to contextual/parent font sizing
rem → relative to root html font size
```

### Tip 💡

`rem` is often easier to manage consistently across a whole website.

---

# 6. `vh`

`vh` = **Viewport Height**

```css
.box {
    height: 50vh;
}
```

`1vh` = 1% of the viewport's height.

So:

```text
50vh = 50% of viewport height
```

Useful when sizing elements relative to the screen height.

---

# 7. `vw`

`vw` = **Viewport Width**

```css
.box {
    width: 50vw;
}
```

`1vw` = 1% of the viewport's width.

So:

```text
50vw = 50% of viewport width
```

---

# 8. Viewport

The **viewport** is the visible area of the webpage in the browser.

```text
┌─────────────────────────────┐
│                             │
│          VIEWPORT           │
│                             │
│                             │
└─────────────────────────────┘
      ← width →
          ↑
        height
```

Therefore:

```text
vw → viewport width
vh → viewport height
```

---

# 9. `vmin`

`vmin` represents **1% of the smaller viewport dimension**.

```css
.box {
    width: 50vmin;
}
```

If:

```text
viewport width  = 1200px
viewport height = 800px
```

The smaller dimension is `800px`.

So:

```text
1vmin = 8px
50vmin = 400px
```

---

# 10. `vmax`

`vmax` represents **1% of the larger viewport dimension**.

Using:

```text
width  = 1200px
height = 800px
```

The larger dimension is `1200px`.

Therefore:

```text
1vmax = 12px
```

---

# 11. Absolute vs Relative Units

### Absolute/fixed-style units

```text
px
```

### Relative units

```text
%
em
rem
vh
vw
vmin
vmax
```

Relative units can adapt based on their reference size.

---

# ⭐ Important Tips

### Remember:

```text
px   → pixels
%    → containing element
em   → contextual font size
rem  → root font size
vh   → viewport height
vw   → viewport width
vmin → smaller viewport dimension
vmax → larger viewport dimension
```

### Easy memory 🧠

```text
em  → element/context
rem → root
vw  → viewport width
vh  → viewport height
```

**Don't blindly use `px` everywhere.** Relative units are important for responsive websites.

---

# ⚡ Quick Revision

| Unit   | Relative to                         |
| ------ | ----------------------------------- |
| `px`   | Fixed CSS pixel unit                |
| `%`    | Containing element/property context |
| `em`   | Contextual/parent font sizing       |
| `rem`  | Root (`html`) font size             |
| `vh`   | Viewport height                     |
| `vw`   | Viewport width                      |
| `vmin` | Smaller viewport dimension          |
| `vmax` | Larger viewport dimension           |

### Most important

```text
em  ≠ rem

em  → contextual
rem → root

vw → width
vh → height
```
