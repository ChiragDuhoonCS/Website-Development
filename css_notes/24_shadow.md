# Video 24 — CSS Shadows & Outlines

This is **Tutorial #24: CSS Shadows and Outlines** from your Sigma playlist. The video covers **box shadows, text shadows, and outlines**. ([YouTube][1])

---

## 1. Box Shadow

`box-shadow` adds a shadow around an element.

### Syntax

```css
box-shadow: h-offset v-offset blur spread color;
```

Example:

```css
.box {
    box-shadow: 5px 5px 15px 5px gray;
}
```

### Parts

```text
5px  → horizontal offset
5px  → vertical offset
15px → blur radius
5px  → spread radius
gray → color
```

### What they do

* **Horizontal offset** → moves shadow left/right.
* **Vertical offset** → moves shadow up/down.
* **Blur** → controls how blurred the shadow is.
* **Spread** → increases/decreases the shadow's size.
* **Color** → shadow color.

---

## 2. Shadow Direction

Example:

```css
box-shadow: 10px 10px 10px gray;
```

```text
        Element
     ┌───────────┐
     │           │
     └───────────┘
          ↘
        Shadow
```

Positive horizontal/vertical values move the shadow **right/down**.

Negative values can move it **left/up**:

```css
box-shadow: -10px -10px 10px gray;
```

---

## 3. `inset`

`inset` makes the shadow appear **inside the element**.

```css
.box {
    box-shadow: inset 5px 5px 10px gray;
}
```

Without `inset`:

```text
┌─────────────┐
│    BOX      │  ← shadow outside
└─────────────┘
```

With `inset`:

```text
┌─────────────┐
│  ↘ shadow   │
│    BOX      │
└─────────────┘
```

### Tip 💡

Remember:

```text
normal → outer shadow
inset  → inner shadow
```

---

# 4. Multiple Box Shadows

You can apply multiple shadows by separating them with commas.

```css
.box {
    box-shadow:
        5px 5px 10px gray,
        -5px -5px 10px black;
}
```

This can create more complex visual effects.

---

# 5. Text Shadow

`text-shadow` applies a shadow to **text** rather than the entire box.

### Syntax

```css
text-shadow: h-offset v-offset blur color;
```

Example:

```css
h1 {
    text-shadow: 2px 2px 4px gray;
}
```

### Difference

```text
box-shadow  → element/box
text-shadow → text
```

---

## 6. Multiple Text Shadows

You can also use multiple text shadows:

```css
h1 {
    text-shadow:
        2px 2px 4px gray,
        -2px -2px 4px black;
}
```

This can be used to create effects such as **glows**.

---

# 7. Outline

An **outline** is a line drawn around an element, outside its border.

### Syntax

```css
outline: width style color;
```

Example:

```css
.box {
    outline: 2px solid red;
}
```

---

## 8. Outline vs Border

Both can look similar, but they are different.

```text
Border
  ↓
┌───────────────┐
│    Element    │
└───────────────┘
       ↑
    Outline
```

### Main difference

**Border:**

* Part of the box model.
* Takes up space in the layout.
* Can be styled individually on different sides.

**Outline:**

* Drawn outside the border.
* Does **not** take up layout space.
* Generally surrounds the element as a whole.

([CodeWithHarry][2])

---

# 9. Outline Styles

Example:

```css
.box {
    outline: 3px dashed black;
}
```

Common styles:

```text
solid
dashed
dotted
double
```

---

# 10. Outline Offset

`outline-offset` controls the distance between the outline and the element.

```css
.box {
    outline: 2px solid red;
    outline-offset: 5px;
}
```

```text
┌─────────────────────┐ ← outline
│   ┌─────────────┐   │
│   │   Element   │   │
│   └─────────────┘   │
└─────────────────────┘
       ↑
   offset/space
```

### Tip 💡

`outline-offset` is useful when you want the outline to sit **away from the element**.

---

# 11. Outline for Focus

Outlines are especially useful for showing when an element has **focus**.

Example:

```css
button:focus {
    outline: 2px solid blue;
}
```

When the button receives focus, the outline appears.

This is also important for **keyboard accessibility**.

---

# ⭐ Important Tips

### Remember the difference:

```text
box-shadow  → shadow around box
text-shadow → shadow around text
outline     → line outside element
```

### `box-shadow`

```css
box-shadow: h-offset v-offset blur spread color;
```

### `text-shadow`

```css
text-shadow: h-offset v-offset blur color;
```

Notice: **text-shadow has no spread value.**

### `outline`

```css
outline: width style color;
```

### Most important:

> **Border affects the box model; outline does not take up layout space.**

---

# ⚡ Quick Revision

```css
/* Box shadow */
.box {
    box-shadow: 5px 5px 10px 2px gray;
}

/* Inner shadow */
.box {
    box-shadow: inset 5px 5px 10px gray;
}

/* Text shadow */
h1 {
    text-shadow: 2px 2px 4px gray;
}

/* Outline */
.box {
    outline: 2px solid red;
}

/* Outline distance */
.box {
    outline-offset: 5px;
}
```

```text
box-shadow  → box
text-shadow → text
outline     → outside the element
inset       → inside shadow
```

[1]: https://www.youtube.com/watch?v=BZJcNU648Tc&utm_source=chatgpt.com "CSS Shadows and Outlines | Sigma Web Development Course - Tutorial #24 - YouTube"
[2]: https://www.codewithharry.com/tutorial/css-shadows?utm_source=chatgpt.com "Shadows | CSS Tutorial | CodeWithHarry"
