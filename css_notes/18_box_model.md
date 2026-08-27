# Video 18 — CSS Box Model: Margin, Padding & Borders

This is **Tutorial #18 — CSS Box Model - Margin, Padding & Borders** from your Sigma playlist. ([Class Central][1])

## 1. CSS Box Model

In CSS, **every HTML element is treated as a box**.

The box model has **4 parts**:

```text
┌───────────────────────────────┐
│            MARGIN             │
│  ┌─────────────────────────┐  │
│  │         BORDER          │  │
│  │  ┌───────────────────┐  │  │
│  │  │      PADDING      │  │  │
│  │  │  ┌─────────────┐  │  │  │
│  │  │  │   CONTENT   │  │  │  │
│  │  │  └─────────────┘  │  │  │
│  │  └───────────────────┘  │  │
│  └─────────────────────────┘  │
└───────────────────────────────┘
```

Order:

```text
Content → Padding → Border → Margin
```

---

# 2. Content

The **content** is the actual material inside the element.

Example:

```html
<div>
    Hello World
</div>
```

Here:

```text
Hello World → content
```

The content can be:

* Text
* Image
* Other HTML elements
* etc.

---

# 3. Padding

**Padding = space between the content and the border.**

```css
div {
    padding: 20px;
}
```

```text
Border
┌──────────────────────┐
│      PADDING          │
│   ┌──────────────┐   │
│   │   CONTENT    │   │
│   └──────────────┘   │
└──────────────────────┘
```

### Important

Padding is **inside** the element's border.

---

## Padding on Individual Sides

```css
div {
    padding-top: 10px;
    padding-right: 20px;
    padding-bottom: 30px;
    padding-left: 40px;
}
```

You can also use shorthand.

```css
div {
    padding: 10px 20px 30px 40px;
}
```

The order is:

```text
Top → Right → Bottom → Left
```

### Easy memory 💡

**TRBL → Top Right Bottom Left**

---

# 4. Border

A **border** surrounds the padding and content.

Basic syntax:

```css
div {
    border: 2px solid black;
}
```

It has three main parts:

```text
border-width
border-style
border-color
```

Example:

```css
div {
    border-width: 2px;
    border-style: solid;
    border-color: black;
}
```

Or shorthand:

```css
div {
    border: 2px solid black;
}
```

---

## Border Styles

Common styles include:

```text
solid
dashed
dotted
double
```

Example:

```css
div {
    border: 2px dashed red;
}
```

---

## Individual Borders

You can style individual sides:

```css
div {
    border-top: 2px solid red;
    border-right: 2px solid blue;
    border-bottom: 2px solid green;
    border-left: 2px solid black;
}
```

---

# 5. Border Radius

`border-radius` makes corners rounded.

```css
div {
    border-radius: 10px;
}
```

Larger value → more rounded corners.

```css
div {
    border-radius: 50%;
}
```

A square element with equal dimensions can become a circle.

### Tip 💡

`border-radius` is extremely common for:

* Buttons
* Cards
* Images
* Profile pictures

---

# 6. Margin

**Margin = space outside the border.**

```css
div {
    margin: 20px;
}
```

```text
        MARGIN
   ┌───────────────┐
   │    BORDER     │
   │ ┌───────────┐ │
   │ │ CONTENT   │ │
   │ └───────────┘ │
   └───────────────┘
```

### Remember

```text
Padding → inside border
Margin  → outside border
```

---

# 7. Margin on Individual Sides

```css
div {
    margin-top: 10px;
    margin-right: 20px;
    margin-bottom: 30px;
    margin-left: 40px;
}
```

Shorthand:

```css
div {
    margin: 10px 20px 30px 40px;
}
```

Order:

```text
Top → Right → Bottom → Left
```

---

# 8. Margin Shorthand

### One value

```css
margin: 20px;
```

All four sides:

```text
Top    = 20px
Right  = 20px
Bottom = 20px
Left   = 20px
```

### Two values

```css
margin: 10px 20px;
```

Means:

```text
Top/Bottom = 10px
Left/Right = 20px
```

### Three values

```css
margin: 10px 20px 30px;
```

Means:

```text
Top    = 10px
Left/Right = 20px
Bottom = 30px
```

### Four values

```css
margin: 10px 20px 30px 40px;
```

```text
Top    = 10px
Right  = 20px
Bottom = 30px
Left   = 40px
```

Same shorthand rule applies to `padding`.

---

# 9. Margin Collapse

An important concept in CSS is **margin collapse**.

When the vertical margins of two block-level elements meet, they can **collapse into a single margin** rather than adding together.

Example:

```css
.box1 {
    margin-bottom: 30px;
}

.box2 {
    margin-top: 20px;
}
```

You might expect:

```text
30px + 20px = 50px
```

But in normal block flow, the margins can collapse, so the resulting gap is generally the **larger margin: 30px**.

### Tip 💡

Margin collapse mainly concerns **vertical margins** of block elements.

---

# 10. Box Model Example

```css
.box {
    width: 300px;
    padding: 20px;
    border: 5px solid black;
    margin: 30px;
}
```

The structure becomes:

```text
Margin: 30px
┌─────────────────────────────┐
│ Border: 5px                 │
│ ┌─────────────────────────┐ │
│ │ Padding: 20px           │ │
│ │ ┌─────────────────────┐ │ │
│ │ │ Content: 300px      │ │ │
│ │ └─────────────────────┘ │ │
│ └─────────────────────────┘ │
└─────────────────────────────┘
```

---

# ⭐ Important Tips

### 1. Remember the order

```text
Content
   ↓
Padding
   ↓
Border
   ↓
Margin
```

### 2. Padding vs Margin

```text
Padding → inside
Margin  → outside
```

### 3. Shorthand

```css
padding: 10px 20px 30px 40px;
```

means:

```text
Top → Right → Bottom → Left
```

### 4. Use `border` shorthand

Instead of:

```css
border-width: 2px;
border-style: solid;
border-color: black;
```

you can write:

```css
border: 2px solid black;
```

### 5. Box model is fundamental

Understanding the box model is essential before learning more advanced CSS layout concepts such as **Flexbox, Grid and positioning**.

---

# ⚡ Quick Revision

```text
CSS BOX MODEL
│
├── Content  → actual content
├── Padding  → space inside border
├── Border   → surrounds content + padding
└── Margin   → space outside border
```

### Shorthand

```css
margin: 10px 20px 30px 40px;
padding: 10px 20px 30px 40px;
```

```text
Top → Right → Bottom → Left
```

### Most important

> **Padding = inside the border**
> **Margin = outside the border**

[1]: https://www.classcentral.com/course/youtube-sigma-web-development-course-web-development-tutorials-in-hindi-513241?utm_source=chatgpt.com "Free Video: Sigma Web Development Course - Complete Web Development in Hindi from CodeWithHarry | Class Central"
