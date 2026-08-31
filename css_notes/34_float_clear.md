# CSS Float & Clear — Tutorial #32

## 1. `float`

The `float` property moves an element to the **left or right** and allows surrounding content to flow around it.

### Syntax

```css
img {
    float: left;
}
```

Main values:

```text
left
right
none
```

---

## 2. `float: left`

```css
img {
    float: left;
}
```

The image moves to the **left**, and text can flow around its right side.

```text
┌────────┐  This is some text
│  IMG   │  flowing around the
│        │  floated image.
└────────┘
```

---

## 3. `float: right`

```css
img {
    float: right;
}
```

The element moves to the **right**, allowing text to flow around its left side.

```text
This is some text        ┌────────┐
flowing around the       │  IMG   │
image.                   │        │
                         └────────┘
```

---

## 4. Why `float` was used

`float` was traditionally used for:

* Wrapping text around images
* Creating layouts/columns

Example:

```css
img {
    float: left;
    margin-right: 10px;
}
```

This places the image on the left and adds space between it and the text.

### 💡 Tip

For **modern page layouts**, prefer **Flexbox or Grid** rather than using floats to build the entire layout.

---

# 5. `clear`

`clear` controls whether an element is allowed to appear beside floated elements.

Syntax:

```css
.element {
    clear: both;
}
```

Values:

```text
left
right
both
none
```

---

## 6. `clear: left`

```css
.box {
    clear: left;
}
```

The element will move below elements floated to the **left**.

---

## 7. `clear: right`

```css
.box {
    clear: right;
}
```

The element will move below elements floated to the **right**.

---

## 8. `clear: both`

```css
.box {
    clear: both;
}
```

The element moves below **both left- and right-floated elements**.

This is commonly used when you want to ensure an element starts after all preceding floats.

```text
┌────────┐       ┌────────┐
│ Float  │       │ Float  │
│  left  │       │ right  │
└────────┘       └────────┘

        ↓ clear: both

┌──────────────────────────┐
│       Next element       │
└──────────────────────────┘
```

---

# 9. `float: none`

Removes floating behavior.

```css
img {
    float: none;
}
```

The element returns to normal flow.

---

# 10. Float + Clear Example

```html
<img src="image.jpg" class="image">

<p>
    Some text that flows around the image.
</p>

<div class="box">
    Next section
</div>
```

```css
.image {
    float: left;
}

.box {
    clear: both;
}
```

The paragraph can flow around the image, while `.box` starts **below the float**.

---

# ⭐ Important Difference

```text
float
  ↓
moves an element left/right
and allows content to flow around it

clear
  ↓
prevents an element from sitting beside floats
```

### Easy memory 🧠

**Float = move aside**
**Clear = get below the float**

---

# ⚡ Quick Revision

```css
/* Float left */
img {
    float: left;
}

/* Float right */
img {
    float: right;
}

/* Remove float */
img {
    float: none;
}

/* Clear left float */
.box {
    clear: left;
}

/* Clear right float */
.box {
    clear: right;
}

/* Clear all floats */
.box {
    clear: both;
}
```

### Most important

```text
float: left/right
        ↓
element moves to a side

clear: both
        ↓
element moves below floats
```
