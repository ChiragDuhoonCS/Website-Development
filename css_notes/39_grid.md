# CSS Grid — Ultimate MasterClass | Tutorial #39

## 1. What is CSS Grid?

**CSS Grid** is a **2-dimensional layout system** used to arrange elements in **rows and columns**.

```css
.container {
    display: grid;
}
```

Unlike Flexbox, which is mainly **one-dimensional**, Grid is designed for **rows + columns together**.

---

# 2. Creating Columns — `grid-template-columns`

Defines the number and size of columns.

```css
.container {
    display: grid;
    grid-template-columns: 200px 200px 200px;
}
```

Creates **3 columns**, each `200px` wide.

```text
┌──────┬──────┬──────┐
│  1   │  2   │  3   │
├──────┼──────┼──────┤
│  4   │  5   │  6   │
└──────┴──────┴──────┘
```

You can use different sizes:

```css
grid-template-columns: 100px 200px 300px;
```

---

# 3. `fr` Unit ⭐

`fr` means **fraction of the available space**.

```css
.container {
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
}
```

The available space is divided equally.

```text
1fr : 1fr : 1fr
 ↓     ↓     ↓
equal equal equal
```

Example:

```css
grid-template-columns: 1fr 2fr;
```

The second column gets **twice the available fraction** of the first.

```text
1fr : 2fr
```

### 💡 Tip

`fr` is extremely useful for **responsive layouts** because you don't have to calculate exact widths.

---

# 4. `grid-template-rows`

Defines row sizes.

```css
.container {
    display: grid;
    grid-template-rows: 100px 200px;
}
```

Creates:

```text
Row 1 → 100px
Row 2 → 200px
```

---

# 5. `repeat()`

Instead of writing:

```css
grid-template-columns: 1fr 1fr 1fr 1fr;
```

you can write:

```css
grid-template-columns: repeat(4, 1fr);
```

Meaning:

```text
4 columns
each = 1fr
```

Another example:

```css
grid-template-columns: repeat(3, 200px);
```

→ 3 columns of `200px`.

---

# 6. `gap`

Creates space between grid items.

```css
.container {
    display: grid;
    gap: 20px;
}
```

You can separately control:

```css
row-gap: 10px;
column-gap: 20px;
```

Or:

```css
gap: 10px 20px;
```

```text
10px → row gap
20px → column gap
```

---

# 7. `grid-template-areas`

Allows you to create a layout using **named areas**.

```css
.container {
    display: grid;

    grid-template-areas:
        "header header"
        "sidebar main"
        "footer footer";
}
```

Then assign areas:

```css
.header {
    grid-area: header;
}

.sidebar {
    grid-area: sidebar;
}

.main {
    grid-area: main;
}

.footer {
    grid-area: footer;
}
```

Conceptually:

```text
┌───────────────┐
│    HEADER     │
├───────┬───────┤
│ SIDE  │ MAIN  │
├───────┴───────┤
│    FOOTER     │
└───────────────┘
```

### ⭐ Tip

`grid-template-areas` makes complex page layouts easier to understand because the CSS visually resembles the layout.

---

# 8. `grid-column`

Controls where an item starts/ends across columns.

```css
.item {
    grid-column: 1 / 3;
}
```

This means the item spans from **grid column line 1 to line 3**, covering two column tracks.

```text
Column lines:

1       2       3
│       │       │
├───────┼───────┤
│   ITEM        │
└───────┴───────┘
```

---

# 9. `grid-row`

Same concept for rows.

```css
.item {
    grid-row: 1 / 3;
}
```

The item spans from row line `1` to row line `3`.

---

# 10. `span`

Instead of specifying the ending line, you can specify how many tracks to span.

```css
.item {
    grid-column: span 2;
}
```

→ Item occupies **2 columns**.

Similarly:

```css
.item {
    grid-row: span 2;
}
```

→ Item occupies **2 rows**.

---

# 11. `justify-items`

Controls the horizontal alignment of items **inside their grid cells**.

```css
.container {
    justify-items: center;
}
```

Common values:

```text
start
end
center
stretch
```

---

# 12. `align-items`

Controls the vertical alignment of items **inside their grid cells**.

```css
.container {
    align-items: center;
}
```

So:

```text
justify-items → horizontal
align-items    → vertical
```

---

# 13. `place-items`

Shorthand for:

```text
align-items
justify-items
```

Example:

```css
.container {
    place-items: center;
}
```

This centers grid items inside their cells in both directions.

---

# 14. `justify-content`

Controls the grid's position along the **horizontal axis** when there is extra space in the grid container.

```css
.container {
    justify-content: center;
}
```

Common values:

```text
start
end
center
space-between
space-around
space-evenly
```

⚠️ Don't confuse:

```text
justify-items
→ items inside their cells

justify-content
→ entire grid inside its container
```

---

# 15. `align-content`

Controls the grid's position along the **vertical axis** when extra space exists.

```css
.container {
    align-content: center;
}
```

---

# 16. `place-content`

Shorthand for:

```text
align-content
justify-content
```

Example:

```css
.container {
    place-content: center;
}
```

---

# 17. `minmax()`

Allows you to specify a **minimum and maximum size** for a grid track.

```css
grid-template-columns: minmax(100px, 1fr);
```

Meaning:

```text
minimum → 100px
maximum → 1fr
```

The column won't become smaller than `100px`, but can grow into available space.

---

# 18. Responsive Grid ⭐

A very useful pattern:

```css
.container {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
    gap: 20px;
}
```

This allows columns to automatically adjust based on available width.

```text
Wide screen:
[1] [2] [3] [4]

Smaller screen:
[1] [2] [3]

Mobile:
[1]
[2]
[3]
```

### 💡 Tip

This pattern is extremely useful for:

* Card layouts
* Product grids
* Image galleries
* Responsive dashboards

---

# 19. `auto-fit` vs `auto-fill`

Both can be used with `repeat()`:

```css
repeat(auto-fit, minmax(200px, 1fr))
```

```css
repeat(auto-fill, minmax(200px, 1fr))
```

Basic difference:

```text
auto-fit
→ fits available tracks to the content

auto-fill
→ tries to fill the available space with tracks
```

For common responsive card grids, `auto-fit` is often the convenient choice.

---

# 20. Grid vs Flexbox ⭐

| Flexbox              | Grid                             |
| -------------------- | -------------------------------- |
| Mainly 1D            | 2D                               |
| Row OR column        | Rows AND columns                 |
| Great for components | Great for page/layout structures |
| Content-oriented     | Layout-oriented                  |

### Example

```text
Flexbox:
[1] [2] [3] [4]

Grid:
[1] [2]
[3] [4]
```

💡 They can also be used **together**.

---

# ⭐ Important Grid Properties

### Container

```css
.container {
    display: grid;

    grid-template-columns: repeat(3, 1fr);
    grid-template-rows: 100px 200px;

    gap: 20px;
}
```

### Item

```css
.item {
    grid-column: 1 / 3;
    grid-row: 1 / 2;
}
```

---

# 💡 Tips

### Remember the difference:

```text
grid-template-columns
→ define columns

grid-template-rows
→ define rows

grid-column
→ position/span an item across columns

grid-row
→ position/span an item across rows
```

### Most useful responsive pattern:

```css
grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
```

### `fr` vs `px`

```text
200px
→ fixed size

1fr
→ flexible fraction of available space
```

---

# ⚡ Quick Revision

```css
.container {
    display: grid;

    /* Columns */
    grid-template-columns: repeat(3, 1fr);

    /* Rows */
    grid-template-rows: 100px 200px;

    /* Gap */
    gap: 20px;

    /* Alignment */
    place-items: center;
}
```

### Responsive:

```css
.container {
    display: grid;
    grid-template-columns:
        repeat(auto-fit, minmax(200px, 1fr));
    gap: 20px;
}
```

### 🧠 Remember

**Grid = Rows + Columns**

```text
grid-template-columns → define columns
grid-template-rows    → define rows
gap                   → spacing
fr                    → flexible fraction
grid-column           → column positioning
grid-row              → row positioning
grid-area             → named area
```
