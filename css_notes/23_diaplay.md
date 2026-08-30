# Video 23 — CSS Display Property

This is **Tutorial #23: CSS Display Property** from your Sigma playlist. The video covers inline/block behavior, `display: none`, `visibility`, Flexbox, and Grid. ([YouTube][1])

## 1. `display` Property

The `display` property controls **how an element behaves in the layout**.

Basic syntax:

```css
selector {
    display: value;
}
```

The video focuses on:

```text
inline
block
inline-block
none
flex
inline-flex
grid
```

---

# 2. Block Elements

A **block-level element** generally starts on a new line and takes the available width.

Example:

```html
<div>I am a box</div>
<div>I am another box</div>
```

They appear one below another.

```text
┌──────────────────────┐
│ I am a box            │
└──────────────────────┘
┌──────────────────────┐
│ I am another box     │
└──────────────────────┘
```

Common block elements include:

```text
div
p
h1 - h6
```

---

# 3. `display: inline`

You can change a block element into an inline element:

```css
div {
    display: inline;
}
```

Now elements can appear **on the same line** when space is available.

```text
Box 1   Box 2   Box 3
```

### Important

Inline elements generally:

* Take only the space required by their content.
* Stay on the same line.
* Don't behave like block elements with respect to width/height.

---

# 4. `display: inline-block`

`inline-block` combines useful characteristics of both.

```css
div {
    display: inline-block;
}
```

It:

* Stays **inline** with other elements.
* Allows you to control **width and height** like a block.

Example:

```css
.box {
    display: inline-block;
    width: 100px;
    height: 100px;
}
```

```text
┌───────┐  ┌───────┐  ┌───────┐
│ Box 1 │  │ Box 2 │  │ Box 3 │
└───────┘  └───────┘  └───────┘
```

### ⭐ Tip

Remember:

```text
inline       → same line, limited sizing behavior
block        → new line, full available width
inline-block → same line + width/height control
```

---

# 5. `display: none`

```css
.box {
    display: none;
}
```

This makes the element disappear **and removes its space from the layout**. ([Code With Harry][2])

Example:

```text
Box 1
Box 2 → display: none
Box 3
```

Result:

```text
Box 1
Box 3
```

There is no empty space where Box 2 was.

### ⭐ Tip

`display: none` means:

> **Element is not displayed and doesn't occupy layout space.**

---

# 6. `visibility: hidden`

```css
.box {
    visibility: hidden;
}
```

The element becomes invisible, **but its space remains reserved**. ([Code With Harry][2])

```text
Box 1
[empty space]
Box 3
```

### Difference

```text
display: none
→ hidden + space removed

visibility: hidden
→ hidden + space remains
```

This distinction is very important.

---

# 7. Changing `display` Back

If an element was hidden using:

```css
.box {
    display: none;
}
```

you can make it visible again by assigning another display value, such as:

```css
.box {
    display: inline-block;
}
```

---

# 8. Flexbox

Flexbox is a CSS layout system used to arrange elements.

Set a container to:

```css
.container {
    display: flex;
}
```

Its children become **flex items**.

One important use shown in the video is centering:

```css
.container {
    display: flex;
    justify-content: center;
}
```

`justify-content: center` centers the flex items along the **main axis**. ([Video Highlight][3])

### Basic idea

```text
Container
┌─────────────────────────────┐
│       [ Box ]               │
└─────────────────────────────┘
          ↑
       centered
```

### ⭐ Tip

You'll learn Flexbox in much greater detail later. For now remember:

```css
display: flex;
```

turns the element into a **flex container**.

---

# 9. `inline-flex`

```css
.container {
    display: inline-flex;
}
```

It behaves like an inline-level element while its children are laid out using Flexbox.

The video demonstrates it as a way to keep the flex container **inline with surrounding content**. ([Video Highlight][3])

---

# 10. CSS Grid

Another layout system is **Grid**.

```css
.container {
    display: grid;
}
```

Grid is designed for arranging elements in **rows and columns**.

```text
┌───────┬───────┬───────┐
│ Box 1 │ Box 2 │ Box 3 │
├───────┼───────┼───────┤
│ Box 4 │ Box 5 │ Box 6 │
└───────┴───────┴───────┘
```

The video introduces Grid here; its detailed properties are covered later. ([Video Highlight][3])

---

# ⭐ Important Tips

### Remember the three basic display behaviors:

```text
block
→ new line + available width

inline
→ same line + content-sized behavior

inline-block
→ same line + width/height control
```

### Most important difference:

```text
display: none
        ↓
element + space disappear

visibility: hidden
        ↓
element disappears
space remains
```

### Layout systems:

```text
Flexbox → mainly one-dimensional layout
Grid    → rows + columns / two-dimensional layout
```

---

# ⚡ Quick Revision

```css
.box {
    display: block;
}

.box {
    display: inline;
}

.box {
    display: inline-block;
}

.box {
    display: none;
}

.box {
    display: flex;
}

.box {
    display: inline-flex;
}

.box {
    display: grid;
}
```

### 🧠 One-line memory

**Block = new line | Inline = same line | Inline-block = same line + sizing | None = remove | Flex = flexible layout | Grid = rows/columns**

[1]: https://www.youtube.com/watch?v=hRHV5cjEB1w&utm_source=chatgpt.com "CSS Display Property | Sigma Web Development Course - Tutorial #23 - YouTube"
[2]: https://www.codewithharry.com/tutorial/css-display?utm_source=chatgpt.com "Display | CSS Tutorial | CodeWithHarry"
[3]: https://videohighlight.com/v/hRHV5cjEB1w?utm_source=chatgpt.com "CSS Display Property | Sigma Web Development Course - Tutorial #23 | YouTube Video Summary | Video Highlight"
