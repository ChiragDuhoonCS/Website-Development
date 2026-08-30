# Video 26 — CSS Overflow

This lecture covers the **`overflow` property** and what happens when content is larger than its container.

---

## 1. What is Overflow?

**Overflow** happens when the content inside an element is too large to fit inside its specified dimensions.

Example:

```css
.box {
    width: 200px;
    height: 100px;
}
```

If the content needs more than `200 × 100px`, it can overflow.

```text
┌──────────────────┐
│  Content         │
│  Content         │
│  Content         │
└──────────────────┘
       ↓
   extra content
```

---

# 2. `overflow`

The `overflow` property controls what happens to content that doesn't fit.

```css
.box {
    overflow: hidden;
}
```

Main values:

```text
visible
hidden
scroll
auto
```

---

## 3. `overflow: visible`

This is the **default**.

```css
.box {
    overflow: visible;
}
```

Content that doesn't fit can appear **outside the box**.

```text
┌──────────────┐
│ Content      │
│ Content      │
└──────────────┘
   Content continues
   outside
```

---

## 4. `overflow: hidden`

```css
.box {
    overflow: hidden;
}
```

Extra content is **clipped/hidden**.

```text
┌──────────────┐
│ Content      │
│ Content      │
└──────────────┘
```

Anything outside the box isn't visible.

### Tip 💡

Useful when you don't want overflowing content to appear outside a container.

---

# 5. `overflow: scroll`

```css
.box {
    overflow: scroll;
}
```

Scrollbars are provided so the user can access content that doesn't fit.

```text
┌──────────────┐
│ Content      │█
│ Content      │█
│ Content      │↓
└──────────────┘
```

Depending on the browser and overflow direction, horizontal/vertical scrolling may be available.

---

# 6. `overflow: auto`

```css
.box {
    overflow: auto;
}
```

The browser adds scrollbars **when necessary**.

This is often more convenient than `scroll`.

```text
Content fits
→ no scrollbar needed

Content overflows
→ scrollbar appears
```

### ⭐ Tip

For many practical situations:

```css
overflow: auto;
```

is preferable when you want scrolling **only when required**.

---

# 7. `overflow-x`

Controls **horizontal overflow**.

```css
.box {
    overflow-x: auto;
}
```

```text
←──────────────→
   horizontal
    scrolling
```

---

# 8. `overflow-y`

Controls **vertical overflow**.

```css
.box {
    overflow-y: auto;
}
```

```text
      ↑
      │
      │ vertical
      │ scrolling
      ↓
```

---

# 9. Different X and Y Values

You can control each direction separately:

```css
.box {
    overflow-x: hidden;
    overflow-y: auto;
}
```

Meaning:

```text
Horizontal → hidden
Vertical   → scroll when needed
```

This is useful when you want to prevent horizontal overflow while still allowing vertical scrolling.

---

# 10. `overflow-wrap`

Long words or strings can sometimes extend beyond the container.

`overflow-wrap` allows the browser to break a long word if necessary.

```css
.box {
    overflow-wrap: break-word;
}
```

This helps prevent long text from escaping the container.

---

# ⭐ Tips

### Remember:

```text
overflow        → both directions
overflow-x      → horizontal
overflow-y      → vertical
```

### Main values:

```text
visible → show outside
hidden  → hide outside
scroll  → provide scrolling
auto    → scroll only when needed
```

### Easy memory 🧠

```text
visible → See it
hidden  → Hide it
scroll  → Scroll it
auto    → Browser decides
```

---

# ⚡ Quick Revision

```css
.box {
    overflow: visible;
}

.box {
    overflow: hidden;
}

.box {
    overflow: scroll;
}

.box {
    overflow: auto;
}
```

Direction-specific:

```css
.box {
    overflow-x: hidden;
    overflow-y: auto;
}
```

### Most important

> **Overflow controls what happens when content doesn't fit inside an element's box.**
