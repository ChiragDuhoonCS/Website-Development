# Video 25 — CSS Styling Lists

## 1. Styling Lists

CSS can change how HTML lists look.

HTML:

```html
<ul>
    <li>Apple</li>
    <li>Banana</li>
    <li>Mango</li>
</ul>
```

The main property used is:

```css
list-style-type
```

---

## 2. `list-style-type`

Controls the **marker/bullet style**.

### Unordered list

```css
ul {
    list-style-type: square;
}
```

Common values:

```text
disc
circle
square
none
```

Example:

```css
ul {
    list-style-type: none;
}
```

Removes the bullets completely.

---

## 3. Ordered List

For `<ol>`, you can change the numbering style.

```css
ol {
    list-style-type: upper-roman;
}
```

Common values:

```text
decimal
lower-alpha
upper-alpha
lower-roman
upper-roman
```

Example:

```css
ol {
    list-style-type: lower-alpha;
}
```

Result:

```text
a. Apple
b. Banana
c. Mango
```

---

## 4. `list-style-position`

Controls where the list marker is positioned.

```css
ul {
    list-style-position: inside;
}
```

Two important values:

```text
outside
inside
```

### `outside`

Default behavior.

```text
• Item
  continues here
```

### `inside`

The marker becomes part of the content's box.

```text
• Item
  continues here
```

The difference becomes more noticeable when the text wraps.

---

## 5. `list-style-image`

You can use an image as the list marker.

```css
ul {
    list-style-image: url("image.png");
}
```

Instead of the normal bullet, the specified image is used.

---

## 6. `list-style` Shorthand

You can combine list-style properties.

```css
ul {
    list-style: square inside;
}
```

You can specify:

```text
list-style-type
list-style-position
list-style-image
```

Example:

```css
ul {
    list-style: square inside;
}
```

---

## 7. Removing List Styling

A common technique for navigation menus:

```css
ul {
    list-style: none;
    padding: 0;
    margin: 0;
}
```

This removes:

* Bullets
* Default padding
* Default margin

### Tip 💡

When creating a navigation bar from a `<ul>`, remember that removing `list-style` alone may **not remove the default spacing**.

---

# ⭐ Tips

* `<ul>` → unordered list → bullets
* `<ol>` → ordered list → numbers/letters
* `list-style-type` → marker type
* `list-style-position` → marker position
* `list-style-image` → custom image marker
* `list-style` → shorthand

### Remember

```text
list-style-type     → WHAT marker?
list-style-position → WHERE marker?
list-style-image    → WHICH image?
```

---

# ⚡ Quick Revision

```css
/* Bullet type */
ul {
    list-style-type: square;
}

/* Number type */
ol {
    list-style-type: upper-roman;
}

/* Marker position */
ul {
    list-style-position: inside;
}

/* Image marker */
ul {
    list-style-image: url("image.png");
}

/* Shorthand */
ul {
    list-style: square inside;
}

/* Remove list styling */
ul {
    list-style: none;
    margin: 0;
    padding: 0;
}
```

**Main takeaway:** `list-style-*` properties control the **appearance, position, and type of list markers**.
