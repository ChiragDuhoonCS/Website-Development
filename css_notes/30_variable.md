# Video 29 — CSS Variables

## 1. What are CSS Variables?

CSS variables are **custom properties** that store values so they can be reused throughout your CSS.

Syntax:

```css
:root {
    --variable-name: value;
}
```

Example:

```css
:root {
    --main-color: blue;
}
```

Use the variable with:

```css
h1 {
    color: var(--main-color);
}
```

Here:

```text
--main-color → variable
blue         → stored value
var()        → retrieves the value
```

---

## 2. Why Use CSS Variables?

Without variables:

```css
h1 {
    color: blue;
}

p {
    color: blue;
}

button {
    background-color: blue;
}
```

If you want to change `blue` to `red`, you have to change it in multiple places.

With a variable:

```css
:root {
    --main-color: blue;
}

h1 {
    color: var(--main-color);
}

p {
    color: var(--main-color);
}

button {
    background-color: var(--main-color);
}
```

Now change only:

```css
--main-color: red;
```

and all related elements update.

### ⭐ Tip

CSS variables are especially useful for maintaining a **consistent theme/design**.

---

# 3. Naming CSS Variables

CSS custom properties must start with **two hyphens**:

```css
--main-color
--font-size
--primary-background
```

Example:

```css
:root {
    --primary-color: blue;
    --secondary-color: yellow;
}
```

Then:

```css
h1 {
    color: var(--primary-color);
}

body {
    background-color: var(--secondary-color);
}
```

---

# 4. `var()` Function

To use a CSS variable:

```css
var(--variable-name)
```

Example:

```css
.box {
    color: var(--main-color);
}
```

You **cannot** simply write:

```css
color: --main-color;
```

❌ Wrong.

Use:

```css
color: var(--main-color);
```

✅ Correct.

---

# 5. Variables in `:root`

A common practice is to define global variables inside `:root`.

```css
:root {
    --main-color: blue;
    --secondary-color: green;
    --font-size: 20px;
}
```

Then use them anywhere:

```css
h1 {
    color: var(--main-color);
}

p {
    color: var(--secondary-color);
    font-size: var(--font-size);
}
```

### Why `:root`?

`:root` represents the document's root element (`html`), so variables defined there are available throughout the document unless overridden by a more specific/local definition.

---

# 6. Local CSS Variables

Variables don't have to be global.

You can define one inside a particular selector:

```css
.box {
    --box-color: red;
    color: var(--box-color);
}
```

The variable is available within that element's scope and its descendants where it is inherited.

Example:

```css
.box {
    --main-color: red;
}

.box p {
    color: var(--main-color);
}
```

---

# 7. Changing a Variable

One major benefit is that you can change the value in one place.

```css
:root {
    --main-color: blue;
}

h1 {
    color: var(--main-color);
}
```

Change:

```css
:root {
    --main-color: red;
}
```

Now the `<h1>` becomes red.

---

# 8. Fallback Value

You can provide a fallback value inside `var()`.

```css
p {
    color: var(--text-color, black);
}
```

Meaning:

```text
If --text-color exists
        ↓
use it

Otherwise
        ↓
use black
```

Syntax:

```css
var(--variable, fallback);
```

---

# 9. CSS Variables with Calculations

Variables can also be used with functions such as `calc()`.

```css
:root {
    --size: 100px;
}

.box {
    width: calc(var(--size) * 2);
}
```

The variable's value is inserted into the calculation.

---

# ⭐ Tips

* CSS variables **start with `--`**.
* Use `var()` to access them.
* `:root` is commonly used for **global variables**.
* Use meaningful names:

```css
--primary-color
--text-color
--border-radius
```

instead of:

```css
--x
--abc
```

* Variables are excellent for **themes, colors, spacing and reusable values**.

### Easy memory 🧠

```text
--name:value
      ↓
   variable

var(--name)
      ↓
   use it
```

---

# ⚡ Quick Revision

```css
:root {
    --main-color: blue;
    --font-size: 20px;
}

h1 {
    color: var(--main-color);
    font-size: var(--font-size);
}
```

### Local variable

```css
.box {
    --box-color: red;
}

.box p {
    color: var(--box-color);
}
```

### Fallback

```css
color: var(--text-color, black);
```

### Remember

> **CSS Variable = store a reusable value → `var()` = use that value.**
