# CSS Flexbox — Ultimate MasterClass | Tutorial #38

## 1. What is Flexbox?

**Flexbox (Flexible Box Layout)** is a CSS layout system used to arrange elements in **rows or columns** and control their alignment, spacing, and size.

To use Flexbox:

```css
.container {
    display: flex;
}
```

The element becomes a **flex container**, and its direct children become **flex items**.

```text
.container
├── item 1
├── item 2
└── item 3
```

---

# 2. `display: flex`

```css
.container {
    display: flex;
}
```

By default, flex items are placed in a **row**.

```text
┌─────┐ ┌─────┐ ┌─────┐
│  1  │ │  2  │ │  3  │
└─────┘ └─────┘ └─────┘
```

---

# 3. Main Axis & Cross Axis

Flexbox works with two axes.

### Default (`row`)

```text
Main axis  → → → → →

Cross axis
    ↓
    ↓
```

* **Main axis** → direction of flex items
* **Cross axis** → perpendicular to main axis

This is important for understanding `justify-content` and `align-items`.

---

# 4. `flex-direction`

Controls the **main-axis direction**.

```css
.container {
    display: flex;
    flex-direction: row;
}
```

Values:

```text
row
row-reverse
column
column-reverse
```

### `row`

```text
1 → 2 → 3
```

Default.

### `row-reverse`

```text
3 → 2 → 1
```

### `column`

```text
1
↓
2
↓
3
```

### `column-reverse`

```text
3
↓
2
↓
1
```

---

# 5. `justify-content`

Controls how flex items are distributed along the **main axis**.

```css
.container {
    justify-content: center;
}
```

Common values:

```text
flex-start
flex-end
center
space-between
space-around
space-evenly
```

### `flex-start`

Items start at the beginning.

```text
[1][2][3]────────
```

### `flex-end`

```text
────────[1][2][3]
```

### `center`

```text
────[1][2][3]────
```

### `space-between`

Equal space **between** items; no extra space at the outer edges.

```text
[1]────[2]────[3]
```

### `space-around`

Space around each item.

### `space-evenly`

Equal spacing between items **and the container edges**.

### ⭐ Tip

`justify-content` follows the **main axis**, so its direction changes when `flex-direction` changes.

---

# 6. `align-items`

Controls alignment along the **cross axis**.

```css
.container {
    align-items: center;
}
```

Common values:

```text
stretch
flex-start
flex-end
center
baseline
```

Example with `row`:

```text
┌──────────────────────┐
│       [1] [2] [3]    │
└──────────────────────┘
```

`align-items: center` centers items vertically.

### ⚠️ Important

With:

```css
flex-direction: row;
```

`align-items` controls **vertical** alignment.

With:

```css
flex-direction: column;
```

it controls **horizontal** alignment.

---

# 7. `align-self`

Allows **one particular flex item** to override the container's `align-items`.

```css
.item2 {
    align-self: flex-end;
}
```

Example:

```css
.container {
    display: flex;
    align-items: center;
}

.item2 {
    align-self: flex-start;
}
```

Only `.item2` gets different cross-axis alignment.

---

# 8. `flex-wrap`

By default, flex items try to remain on one line.

```css
.container {
    display: flex;
    flex-wrap: wrap;
}
```

Values:

```text
nowrap
wrap
wrap-reverse
```

### `nowrap`

```text
[1][2][3][4][5][6] → same line
```

### `wrap`

Items move to the next line when necessary.

```text
[1][2][3][4]
[5][6]
```

---

# 9. `align-content`

Controls the spacing/alignment of **multiple flex lines** when wrapping occurs.

```css
.container {
    display: flex;
    flex-wrap: wrap;
    align-content: center;
}
```

⚠️ `align-content` matters when there are **multiple flex lines**.

It is different from `align-items`.

```text
align-items
→ items within a flex line

align-content
→ flex lines within the container
```

---

# 10. `gap`

Creates space between flex items.

```css
.container {
    display: flex;
    gap: 20px;
}
```

You can also specify row and column gaps:

```css
.container {
    row-gap: 10px;
    column-gap: 20px;
}
```

Or:

```css
.container {
    gap: 10px 20px;
}
```

```text
10px → row gap
20px → column gap
```

### ⭐ Tip

`gap` is generally cleaner than adding margins to every flex item just to create spacing.

---

# 11. `order`

Controls the visual order of flex items.

Default:

```css
.item {
    order: 0;
}
```

Example:

```css
.item1 {
    order: 3;
}

.item2 {
    order: 1;
}

.item3 {
    order: 2;
}
```

Visual order:

```text
2 → 3 → 1
```

Items with lower `order` values appear first.

### Tip 💡

`order` changes **visual layout order**, but not necessarily the underlying HTML/DOM order. Don't use it carelessly when logical reading order matters.

---

# 12. `flex-grow`

Controls how much a flex item can **grow** when extra space is available.

```css
.item {
    flex-grow: 1;
}
```

Example:

```css
.item1 {
    flex-grow: 1;
}

.item2 {
    flex-grow: 2;
}
```

The available extra space is distributed according to the grow factors.

```text
item 1 → 1 part
item 2 → 2 parts
```

---

# 13. `flex-shrink`

Controls how much a flex item can **shrink** when there isn't enough space.

```css
.item {
    flex-shrink: 1;
}
```

Default is generally:

```text
1
```

If:

```css
.item1 {
    flex-shrink: 0;
}
```

that item won't shrink due to flex shrinking.

---

# 14. `flex-basis`

Defines the item's **initial main size** before remaining space is distributed.

```css
.item {
    flex-basis: 200px;
}
```

With:

```css
flex-direction: row;
```

it acts along the horizontal main axis.

With:

```css
flex-direction: column;
```

it acts along the vertical main axis.

---

# 15. `flex` Shorthand

Combines:

```text
flex-grow
flex-shrink
flex-basis
```

Example:

```css
.item {
    flex: 1;
}
```

A common layout pattern:

```css
.item {
    flex: 1;
}
```

This allows multiple flex items to share available space.

Explicit form:

```css
.item {
    flex: 1 1 0;
}
```

Meaning:

```text
grow   = 1
shrink = 1
basis  = 0
```

---

# 16. `align-items` vs `align-content`

Very important difference:

```text
align-items
     ↓
alignment of items within a flex line

align-content
     ↓
alignment of multiple flex lines
```

`align-content` has little/no effect when there is only **one flex line**.

---

# 17. Centering with Flexbox ⭐

One of the most useful patterns:

```css
.container {
    display: flex;
    justify-content: center;
    align-items: center;
}
```

This centers the items on both axes when using the default `row` direction.

```text
┌──────────────────────┐
│                      │
│      [ CONTENT ]     │
│                      │
└──────────────────────┘
```

---

# 18. Complete Example

```html
<div class="container">
    <div class="item">1</div>
    <div class="item">2</div>
    <div class="item">3</div>
</div>
```

```css
.container {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    align-items: center;
    gap: 20px;
}

.item {
    flex: 1;
}
```

This creates a flexible layout where the items can wrap and share available space.

---

# ⭐ Flexbox Cheat Sheet

| Property          | Controls                        |
| ----------------- | ------------------------------- |
| `display: flex`   | Creates flex container          |
| `flex-direction`  | Main-axis direction             |
| `justify-content` | Main-axis alignment             |
| `align-items`     | Cross-axis item alignment       |
| `align-self`      | One item's cross-axis alignment |
| `flex-wrap`       | Wrapping                        |
| `align-content`   | Multiple flex-line alignment    |
| `gap`             | Space between items             |
| `order`           | Visual order                    |
| `flex-grow`       | Growing                         |
| `flex-shrink`     | Shrinking                       |
| `flex-basis`      | Initial main size               |
| `flex`            | Grow + shrink + basis           |

---

# 💡 Important Tips

### 1. Always identify the axes first

```text
flex-direction: row
→ main = horizontal
→ cross = vertical

flex-direction: column
→ main = vertical
→ cross = horizontal
```

Then remember:

```text
justify-content → MAIN axis
align-items     → CROSS axis
```

### 2. `align-content` ≠ `align-items`

`align-content` needs multiple flex lines to have a useful effect.

### 3. `gap` is your friend

Instead of:

```css
.item {
    margin-right: 20px;
}
```

you can often use:

```css
.container {
    gap: 20px;
}
```

### 4. Flexbox is mainly **one-dimensional**

Flexbox primarily handles layout along **one main axis at a time**.

For two-dimensional row + column layouts, **CSS Grid** is often more suitable.

---

# ⚡ Quick Revision

```css
.container {
    display: flex;

    flex-direction: row;

    justify-content: center;
    align-items: center;

    flex-wrap: wrap;
    gap: 20px;
}
```

### Flex item properties:

```css
.item {
    order: 1;
    flex-grow: 1;
    flex-shrink: 1;
    flex-basis: 200px;
}
```

Or:

```css
.item {
    flex: 1;
}
```

### 🧠 Most important memory

```text
                 FLEXBOX
                    │
          ┌─────────┴─────────┐
          ↓                   ↓
      MAIN AXIS           CROSS AXIS
          │                   │
 justify-content         align-items
                          align-self

flex-direction → decides the axes
flex-wrap       → allows new lines
gap             → spacing
```

**Master these 5 first:** `display: flex` → `flex-direction` → `justify-content` → `align-items` → `gap`.
