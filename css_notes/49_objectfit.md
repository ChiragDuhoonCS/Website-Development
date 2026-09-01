# CSS `object-fit` & `object-position` — Tutorial #49

## 1. Why `object-fit`?

When an image/video is placed inside a box with a fixed width and height, its **original aspect ratio** may not match the box.

```css
img {
    width: 300px;
    height: 200px;
}
```

If the image has a different aspect ratio, it may look **stretched or distorted**.

`object-fit` controls **how the content fits inside its box**.

---

## 2. `object-fit: fill`

```css
img {
    width: 300px;
    height: 200px;
    object-fit: fill;
}
```

Default value.

The image is **stretched to completely fill the box**.

⚠️ Aspect ratio can be distorted.

---

## 3. `object-fit: contain`

```css
img {
    object-fit: contain;
}
```

The entire image remains visible while maintaining its **aspect ratio**.

If the image and box have different proportions, empty space may remain.

```text
┌─────────────────────┐
│     ┌─────────┐     │
│     │  IMAGE  │     │
│     └─────────┘     │
└─────────────────────┘
```

### Remember

**contain → show the complete image**

---

## 4. `object-fit: cover`

```css
img {
    object-fit: cover;
}
```

The image maintains its aspect ratio and **completely covers the box**.

If necessary, parts of the image are **cropped**.

```text
┌─────────────────────┐
│  ─── IMAGE ──────   │
│    IMAGE            │
│  ─── IMAGE ──────   │
└─────────────────────┘
```

### ⭐ Important

`cover` is commonly used for:

* Card images
* Profile images
* Banners
* Thumbnails

**cover → fill the box, crop excess**

---

## 5. `object-fit: none`

```css
img {
    object-fit: none;
}
```

The replaced element's content keeps its **original size** instead of being resized to fit the box.

Parts can therefore be clipped if they don't fit.

---

## 6. `object-fit: scale-down`

```css
img {
    object-fit: scale-down;
}
```

The browser chooses whichever results in the **smaller rendered size** between `none` and `contain`.

---

# 7. `object-position`

`object-position` controls **where the image/content is positioned inside its box**.

```css
img {
    width: 300px;
    height: 200px;
    object-fit: cover;
    object-position: center;
}
```

Default position is generally:

```css
object-position: 50% 50%;
```

---

## 8. Position Values

You can use keywords:

```css
object-position: center;
object-position: top;
object-position: bottom;
object-position: left;
object-position: right;
```

For example:

```css
img {
    object-fit: cover;
    object-position: top;
}
```

The image is positioned toward the **top**, which is useful when the important part of the image is near the top.

---

## 9. Using Percentages

You can also specify exact positions:

```css
img {
    object-fit: cover;
    object-position: 20% 80%;
}
```

```text
20% → horizontal position
80% → vertical position
```

You can also use lengths:

```css
object-position: 10px 20px;
```

---

# 10. `object-fit` vs `background-size`

For an actual `<img>`:

```css
img {
    object-fit: cover;
}
```

For a background image:

```css
.box {
    background-size: cover;
}
```

They solve similar **fitting** problems but work on different things:

```text
object-fit     → replaced elements like img/video
background-size → CSS background images
```

---

# ⭐ Most Important Comparison

Suppose:

```css
img {
    width: 300px;
    height: 200px;
}
```

| Value        | What happens                               |
| ------------ | ------------------------------------------ |
| `fill`       | Fills box, may distort                     |
| `contain`    | Entire image visible, empty space possible |
| `cover`      | Fills box, may crop                        |
| `none`       | Keeps intrinsic size                       |
| `scale-down` | Smaller of `none` and `contain`            |

### 🧠 Easy memory

**`contain` = Don't crop**
**`cover` = Don't leave empty space**

---

# 💡 Tips

### For most card/thumbnail designs:

```css
img {
    width: 100%;
    height: 200px;
    object-fit: cover;
}
```

### For showing the complete image:

```css
object-fit: contain;
```

### If the wrong part gets cropped:

Don't change `object-fit` immediately. Try:

```css
object-position: top;
```

or:

```css
object-position: center;
```

---

# ⚡ Quick Revision

```css
/* Stretch to fill */
img {
    object-fit: fill;
}

/* Entire image visible */
img {
    object-fit: contain;
}

/* Fill box + crop if needed */
img {
    object-fit: cover;
}

/* Control crop/focus position */
img {
    object-fit: cover;
    object-position: center top;
}
```

### 🔥 Remember

```text
object-fit
     ↓
How should the image fit?

object-position
     ↓
Where should the image/content be placed?
```
