# Video 19 — CSS Fonts, Text & Color Properties

## 1. Font Family

`font-family` specifies which font should be used.

```css
p {
    font-family: Arial;
}
```

You can provide fallback fonts:

```css
p {
    font-family: Arial, sans-serif;
}
```

The browser tries the fonts from **left to right**.

### Tip 💡

Always keep a fallback font such as `sans-serif`.

---

## 2. Font Size

`font-size` controls the size of text.

```css
p {
    font-size: 20px;
}
```

Common units:

```text
px
em
rem
%
```

---

## 3. Font Style

Controls the style of the text.

```css
p {
    font-style: italic;
}
```

Common values:

```text
normal
italic
oblique
```

---

## 4. Font Weight

Controls the **thickness** of text.

```css
p {
    font-weight: bold;
}
```

You can also use numbers:

```css
p {
    font-weight: 700;
}
```

Common values:

```text
400 → normal
700 → bold
```

---

# 5. Text Decoration

`text-decoration` adds/removes decoration.

```css
p {
    text-decoration: underline;
}
```

Common values:

```text
underline
overline
line-through
none
```

Example:

```css
a {
    text-decoration: none;
}
```

This removes the default underline from a link.

### Tip 💡

`text-decoration: none;` is commonly used when designing navigation links.

---

# 6. Text Transform

Changes the capitalization of text.

```css
p {
    text-transform: uppercase;
}
```

Common values:

```text
uppercase
lowercase
capitalize
none
```

Example:

```text
hello world
     ↓
HELLO WORLD
```

---

# 7. Text Alignment

`text-align` controls horizontal alignment.

```css
p {
    text-align: center;
}
```

Common values:

```text
left
right
center
justify
```

Example:

```css
h1 {
    text-align: center;
}
```

---

# 8. Text Indent

`text-indent` controls the indentation of the **first line**.

```css
p {
    text-indent: 40px;
}
```

Example:

```text
    This is the first line.
This is the second line.
This is the third line.
```

---

# 9. Letter Spacing

`letter-spacing` controls the space between individual letters.

```css
p {
    letter-spacing: 2px;
}
```

```text
Normal → Hello
2px    → H e l l o
```

---

# 10. Word Spacing

`word-spacing` controls the space between words.

```css
p {
    word-spacing: 10px;
}
```

---

# 11. Line Height

`line-height` controls the vertical spacing between lines.

```css
p {
    line-height: 1.5;
}
```

Example:

```text
Line one

Line two

Line three
```

### Tip 💡

Increasing `line-height` can make paragraphs much easier to read.

---

# 12. Text Decoration Properties

Instead of only using `text-decoration`, you can control individual parts.

```css
p {
    text-decoration-line: underline;
    text-decoration-color: red;
    text-decoration-style: solid;
    text-decoration-thickness: 2px;
}
```

### Main properties

```text
text-decoration-line
text-decoration-color
text-decoration-style
text-decoration-thickness
```

---

# 13. Colors in CSS

The `color` property changes **text color**.

```css
p {
    color: red;
}
```

CSS supports different color formats.

---

## 14. Color Names

```css
p {
    color: red;
}
```

Examples:

```text
red
blue
green
yellow
black
white
```

---

# 15. Hexadecimal Colors

Hex colors use:

```text
#RRGGBB
```

Example:

```css
p {
    color: #ff0000;
}
```

Structure:

```text
# R R G G B B
  └─┬─┘ └─┬─┘
   Red    Green/Blue
```

More clearly:

```text
RR → Red
GG → Green
BB → Blue
```

Examples:

```text
#ff0000 → Red
#00ff00 → Green
#0000ff → Blue
#000000 → Black
#ffffff → White
```

### Tip 💡

Hexadecimal colors are extremely common in real-world CSS.

---

# 16. RGB Colors

**RGB = Red, Green, Blue**

Syntax:

```css
p {
    color: rgb(255, 0, 0);
}
```

Each value generally ranges from:

```text
0 → 255
```

Examples:

```css
color: rgb(255, 0, 0); /* red */
color: rgb(0, 255, 0); /* green */
color: rgb(0, 0, 255); /* blue */
```

---

# 17. RGBA

**RGBA = Red + Green + Blue + Alpha**

Syntax:

```css
p {
    color: rgba(255, 0, 0, 0.5);
}
```

```text
R → Red
G → Green
B → Blue
A → Alpha/transparency
```

Alpha commonly ranges from:

```text
0 → completely transparent
1 → completely opaque
```

Example:

```text
0.5 → 50% transparency
```

---

# 18. Background Color

`background-color` changes the background of an element.

```css
div {
    background-color: yellow;
}
```

You can use different color formats:

```css
div {
    background-color: #ffff00;
}
```

or:

```css
div {
    background-color: rgb(255, 255, 0);
}
```

---

# ⭐ Tips

* `font-family` → **which font**
* `font-size` → **how big**
* `font-style` → **italic/normal**
* `font-weight` → **thickness**
* `text-align` → **alignment**
* `text-decoration` → **decoration**
* `text-transform` → **capitalization**
* `letter-spacing` → **space between letters**
* `word-spacing` → **space between words**
* `line-height` → **space between lines**
* `color` → **text color**
* `background-color` → **background color**

### Easy memory

```text
FONT  → appearance of letters
TEXT  → arrangement/spacing
COLOR → colors
```

---

# ⚡ Quick Revision

```css
p {
    font-family: Arial;
    font-size: 20px;
    font-style: italic;
    font-weight: bold;

    color: red;
    background-color: yellow;

    text-align: center;
    text-decoration: underline;
    text-transform: uppercase;

    letter-spacing: 2px;
    word-spacing: 5px;
    line-height: 1.5;
}
```

### Color formats

```text
Name → red
Hex  → #ff0000
RGB  → rgb(255, 0, 0)
RGBA → rgba(255, 0, 0, 0.5)
```

**Remember:** `font → text → color` covers the main focus of this lecture.
