# Video 15 — Ways to Add CSS

CSS can be added to HTML in **3 ways**:

```text
1. Inline CSS
2. Internal CSS
3. External CSS
```

---

## 1. Inline CSS

CSS is written directly inside the HTML element using the `style` attribute.

```html
<h1 style="color: red;">
    Hello World
</h1>
```

### Example with multiple properties

```html
<p style="color: red; background-color: yellow;">
    Hello
</p>
```

Here:

```text
style → attribute
color → property
red   → value
```

### When to use?

Useful when you want to style **one specific element**.

### Tip 💡

Avoid using lots of inline CSS in large projects. It becomes difficult to manage when many elements need the same styling.

---

# 2. Internal CSS

CSS is written inside the `<style>` tag, usually within `<head>`.

```html
<head>
    <style>
        h1 {
            color: red;
        }

        p {
            color: blue;
        }
    </style>
</head>
```

Now every matching `<h1>` and `<p>` on that page receives the specified styling.

### Advantage

Instead of repeating:

```html
<h1 style="color:red;">
<h1 style="color:red;">
<h1 style="color:red;">
```

you can write:

```css
h1 {
    color: red;
}
```

once.

### Tip 💡

Internal CSS is useful when the styling is needed for **one HTML page**.

---

# 3. External CSS

CSS is written in a separate `.css` file.

### `style.css`

```css
h1 {
    color: red;
}

p {
    color: blue;
}
```

Then connect it to HTML:

```html
<head>
    <link rel="stylesheet" href="style.css">
</head>
```

### Important parts

```html
<link rel="stylesheet" href="style.css">
```

* `<link>` → connects an external resource.
* `rel="stylesheet"` → tells the browser it is a stylesheet.
* `href="style.css"` → location of the CSS file.

---

## 4. Why External CSS?

Suppose you have:

```text
index.html
about.html
contact.html
```

All three pages can use the same:

```text
style.css
```

```text
        style.css
        /   |   \
       ↓    ↓    ↓
   index  about contact
```

This avoids writing the same CSS repeatedly.

### Tip 💡

For a **multi-page website**, external CSS is usually the most practical approach.

---

# 5. Comparison

| Type     | Where CSS is written      | Best for                |
| -------- | ------------------------- | ----------------------- |
| Inline   | `style=""` inside element | One specific element    |
| Internal | `<style>` in HTML         | One page                |
| External | Separate `.css` file      | Multiple pages/projects |

### Easy way to remember

```text
Inline   → 1 element
Internal → 1 page
External → multiple pages
```

---

# 6. Example: Same Styling in All Three Ways

### Inline

```html
<h1 style="color: red;">Hello</h1>
```

### Internal

```html
<style>
    h1 {
        color: red;
    }
</style>
```

### External

**HTML:**

```html
<link rel="stylesheet" href="style.css">
```

**style.css:**

```css
h1 {
    color: red;
}
```

All three can produce the same visual result.

---

# ⭐ Tips

* **Inline:** quick but avoid overusing it.
* **Internal:** convenient for a single page.
* **External:** best for reusable CSS and larger projects.
* Remember the connection syntax:

```html
<link rel="stylesheet" href="style.css">
```

* Keep HTML focused on **structure** and CSS focused on **styling**.

---

# ⚡ Quick Revision

```text
3 ways to add CSS:

1. Inline
   <h1 style="color:red;">

2. Internal
   <style>
       h1 { color:red; }
   </style>

3. External
   <link rel="stylesheet" href="style.css">
```

**Remember:**
**Inline → element | Internal → page | External → reusable stylesheet**
