# CSS Filters — Tutorial #50

## 1. What are CSS Filters?

The `filter` property applies **visual effects** to elements, especially images.

```css
img {
    filter: blur(5px);
}
```

Filters can change things like:

* Blur
* Brightness
* Contrast
* Grayscale
* Saturation
* Hue

---

## 2. `blur()`

Blurs an element.

```css
img {
    filter: blur(5px);
}
```

Higher value → more blur.

```css
filter: blur(0px);  /* no blur */
filter: blur(10px); /* more blur */
```

---

## 3. `brightness()`

Controls brightness.

```css
img {
    filter: brightness(150%);
}
```

Values:

```text
100% → normal
>100% → brighter
<100% → darker
0% → completely black
```

Example:

```css
filter: brightness(50%);
```

→ makes the image darker.

---

## 4. `contrast()`

Controls the difference between light and dark areas.

```css
img {
    filter: contrast(150%);
}
```

```text
100% → normal
>100% → more contrast
<100% → less contrast
```

---

## 5. `grayscale()`

Converts the element toward grayscale.

```css
img {
    filter: grayscale(100%);
}
```

```text
0%   → normal colors
100% → completely grayscale
```

Useful for creating black-and-white images.

---

## 6. `sepia()`

Gives an image a **sepia/brownish tone**.

```css
img {
    filter: sepia(100%);
}
```

```text
0%   → no sepia
100% → maximum sepia
```

---

## 7. `saturate()`

Controls color intensity.

```css
img {
    filter: saturate(200%);
}
```

```text
100% → normal
>100% → more vivid colors
<100% → less vivid colors
0% → no saturation
```

---

## 8. `hue-rotate()`

Rotates the colors around the color wheel.

```css
img {
    filter: hue-rotate(90deg);
}
```

Uses an angle:

```text
0deg
90deg
180deg
360deg
```

It changes the **hue**, not the brightness.

---

## 9. `invert()`

Inverts the colors.

```css
img {
    filter: invert(100%);
}
```

```text
0%   → normal
100% → fully inverted
```

Example:

```css
img {
    filter: invert(1);
}
```

The filter functions can accept values in different forms depending on the function; for `invert()`, `1` represents 100%.

---

## 10. `opacity()`

Controls transparency.

```css
img {
    filter: opacity(50%);
}
```

```text
100% → fully visible
50%  → half transparent
0%   → completely transparent
```

💡 CSS also has the separate `opacity` property:

```css
img {
    opacity: 0.5;
}
```

---

# 11. Multiple Filters

You can apply multiple filters together.

```css
img {
    filter: grayscale(100%) blur(2px) brightness(120%);
}
```

They are applied **in the order written**.

Example:

```css
filter: brightness(120%) contrast(150%) grayscale(50%);
```

---

# 12. Removing a Filter

Use:

```css
img {
    filter: none;
}
```

This removes the applied filters.

---

# 13. Filters with Hover

Filters are commonly combined with `:hover`.

```css
img {
    filter: grayscale(100%);
    transition: filter 0.3s;
}

img:hover {
    filter: grayscale(0%);
}
```

Result:

```text
Normal → black & white
Hover  → original colors
```

This creates a smooth image effect.

---

# ⭐ Important Filter Functions

| Filter         | Purpose                |
| -------------- | ---------------------- |
| `blur()`       | Blur                   |
| `brightness()` | Brightness             |
| `contrast()`   | Contrast               |
| `grayscale()`  | Black & white          |
| `sepia()`      | Brown/old-photo effect |
| `saturate()`   | Color intensity        |
| `hue-rotate()` | Change hue             |
| `invert()`     | Invert colors          |
| `opacity()`    | Transparency           |

---

# 💡 Tips

### Easy memory:

```text
blur       → blur
brightness → light/dark
contrast   → light vs dark difference
grayscale  → remove colors
sepia      → old-photo tone
saturate   → color intensity
hue-rotate → change colors
invert     → reverse colors
opacity    → transparency
```

### Very useful combination:

```css
img {
    filter: grayscale(100%);
}

img:hover {
    filter: grayscale(0%);
}
```

Add a transition for a smooth effect:

```css
img {
    filter: grayscale(100%);
    transition: filter 0.3s;
}
```

---

# ⚡ Quick Revision

```css
/* Blur */
filter: blur(5px);

/* Brightness */
filter: brightness(150%);

/* Contrast */
filter: contrast(150%);

/* Grayscale */
filter: grayscale(100%);

/* Sepia */
filter: sepia(100%);

/* Saturation */
filter: saturate(200%);

/* Hue */
filter: hue-rotate(90deg);

/* Invert */
filter: invert(100%);

/* Transparency */
filter: opacity(50%);

/* Multiple */
filter: grayscale(100%) blur(2px);

/* Remove */
filter: none;
```

### 🧠 Remember

**`filter` = apply visual effects to an element.**
