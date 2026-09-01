# CSS Transforms MasterClass — Tutorial #42

## 1. What is `transform`?

`transform` is used to **move, rotate, scale, or skew** an element.

```css
.box {
    transform: rotate(45deg);
}
```

Transforms visually change an element **without changing the normal flow/layout around it**.

---

## 2. `translate()`

Moves an element from its current position.

```css
.box {
    transform: translate(50px, 20px);
}
```

```text
50px → X-axis → right
20px → Y-axis → down
```

### Separate axes

```css
transform: translateX(50px);
transform: translateY(20px);
```

* `translateX()` → horizontal movement
* `translateY()` → vertical movement

---

## 3. `scale()`

Changes the size of an element.

```css
.box {
    transform: scale(2);
}
```

```text
1   → original size
2   → 2× size
0.5 → half size
```

You can scale X and Y separately:

```css
transform: scale(2, 1);
```

---

## 4. `rotate()`

Rotates an element.

```css
.box {
    transform: rotate(45deg);
}
```

```text
45deg   → 45°
90deg   → quarter turn
180deg  → half turn
360deg  → full turn
```

Negative values rotate in the opposite direction:

```css
transform: rotate(-45deg);
```

---

## 5. `skew()`

Slants/distorts an element.

```css
.box {
    transform: skew(20deg, 10deg);
}
```

Separate axes:

```css
transform: skewX(20deg);
transform: skewY(10deg);
```

```text
skewX → horizontal slant
skewY → vertical slant
```

---

# 6. Combining Transform Functions

Multiple transformations can be written together:

```css
.box {
    transform: translateX(50px) rotate(45deg) scale(1.2);
}
```

### ⚠️ Important

**The order matters.**

```css
transform: translateX(50px) rotate(45deg);
```

can produce a different result from:

```css
transform: rotate(45deg) translateX(50px);
```

---

# 7. `transform-origin`

By default, transformations generally happen around the **center** of the element.

You can change the transformation point:

```css
.box {
    transform-origin: top left;
    transform: rotate(45deg);
}
```

Common values:

```text
center
top
bottom
left
right
top left
top right
bottom left
bottom right
```

### Example

```css
.box {
    transform-origin: top left;
}
```

Now the top-left corner acts as the pivot point.

---

# 8. Transform with Hover

Transforms are commonly used with `:hover`.

```css
.box:hover {
    transform: scale(1.1);
}
```

When the mouse enters the element, it becomes larger.

For a smooth effect:

```css
.box {
    transition: transform 0.3s;
}

.box:hover {
    transform: scale(1.1);
}
```

### 💡 Tip

`transform + transition` is commonly used for:

* Button effects
* Cards
* Images
* Navigation elements
* Hover animations

---

# 9. Transform and Layout

A transformed element is visually moved/scaled/rotated, but its **original position in normal flow remains**.

Example:

```css
.box {
    transform: translateX(100px);
}
```

The box appears 100px to the right, but surrounding elements don't rearrange as if the box had actually moved in normal layout.

---

# 10. 2D Transform Functions

The main 2D transforms are:

```text
translate()
scale()
rotate()
skew()
```

Think:

```text
translate → MOVE
scale     → RESIZE
rotate    → TURN
skew      → SLANT
```

---

# 11. 3D Transform Basics

CSS also supports 3D transformations.

Examples:

```css
transform: rotateX(45deg);
transform: rotateY(45deg);
transform: rotateZ(45deg);
```

```text
rotateX → rotate around X-axis
rotateY → rotate around Y-axis
rotateZ → rotate around Z-axis
```

For 3D effects, properties such as `perspective` can be used to create depth.

Example:

```css
.container {
    perspective: 500px;
}
```

---

# ⭐ Tips

### Memorize these first:

```css
transform: translate(50px, 20px);
transform: scale(1.5);
transform: rotate(45deg);
transform: skew(20deg);
```

### Axis memory:

```text
X → horizontal
Y → vertical
Z → depth/3D
```

### Don't confuse:

```text
transform
→ changes the visual transformation

transition
→ controls how smoothly a change happens
```

Example:

```css
.box {
    transition: transform 0.3s;
}

.box:hover {
    transform: scale(1.1);
}
```

---

# ⚡ Quick Revision

```css
/* Move */
transform: translate(50px, 20px);

/* Horizontal move */
transform: translateX(50px);

/* Vertical move */
transform: translateY(20px);

/* Scale */
transform: scale(1.5);

/* Rotate */
transform: rotate(45deg);

/* Skew */
transform: skew(20deg);

/* Change pivot */
transform-origin: top left;
```

### 🧠 One-line memory

**Translate = Move | Scale = Resize | Rotate = Turn | Skew = Slant | Origin = Pivot point | Transition = Smooth change**
