# CSS Transition Property — Tutorial #45

## 1. What is Transition?

The `transition` property makes a CSS property change **smoothly over a period of time** instead of changing instantly.

Without transition:

```text
Normal → Hover
  └──── instant change
```

With transition:

```text
Normal → gradually changes → Hover
```

---

## 2. Basic Syntax

```css
.box {
    transition: property duration;
}
```

Example:

```css
.box {
    transition: background-color 1s;
}
```

Now a background-color change takes **1 second**.

---

# 3. Transition with `:hover`

A common use is with hover:

```css
.box {
    background-color: red;
    transition: background-color 1s;
}

.box:hover {
    background-color: blue;
}
```

When the mouse moves over the box, the color changes smoothly.

### ⭐ Important

Put `transition` on the **original element**, not only on `:hover`.

✅

```css
.box {
    transition: 1s;
}

.box:hover {
    background-color: blue;
}
```

This allows the transition to work when entering **and leaving** the hover state.

---

# 4. `transition-duration`

Controls **how long** the transition takes.

```css
.box {
    transition-duration: 2s;
}
```

Examples:

```text
0.2s → fast
1s   → one second
2s   → two seconds
```

---

# 5. `transition-property`

Specifies **which CSS property** should transition.

```css
.box {
    transition-property: background-color;
}
```

Multiple properties:

```css
.box {
    transition-property: background-color, transform;
}
```

You can also use:

```css
.box {
    transition-property: all;
}
```

This allows all animatable changes to transition.

### 💡 Tip

For better control/performance, it's often preferable to specify the properties you actually need rather than blindly using `all`.

---

# 6. `transition-timing-function`

Controls **the speed pattern** of the transition.

```css
.box {
    transition-timing-function: ease;
}
```

Common values:

```text
ease
linear
ease-in
ease-out
ease-in-out
```

### Meaning

```text
linear
→ constant speed

ease
→ starts/ends more gradually

ease-in
→ starts slowly

ease-out
→ ends slowly

ease-in-out
→ starts and ends slowly
```

---

# 7. `transition-delay`

Controls how long the browser waits **before starting** the transition.

```css
.box {
    transition-delay: 1s;
}
```

Meaning:

```text
Hover
  ↓
wait 1 second
  ↓
transition starts
```

---

# 8. Transition Shorthand

Instead of writing every property separately:

```css
.box {
    transition-property: transform;
    transition-duration: 1s;
    transition-timing-function: ease;
    transition-delay: 0s;
}
```

You can write:

```css
.box {
    transition: transform 1s ease 0s;
}
```

### Order

```text
property
duration
timing-function
delay
```

So:

```css
transition: transform 1s ease 0s;
```

means:

```text
transform → property
1s        → duration
ease      → timing function
0s        → delay
```

---

# 9. Multiple Transitions

Different properties can have different transition settings.

```css
.box {
    transition:
        background-color 1s ease,
        transform 0.5s ease;
}
```

So:

```text
background-color → 1 second
transform        → 0.5 second
```

---

# 10. Transition vs Transform

These are **not the same thing**.

### `transform`

Actually performs the transformation:

```css
.box:hover {
    transform: scale(1.2);
}
```

### `transition`

Controls how smoothly that change happens:

```css
.box {
    transition: transform 0.5s;
}
```

Together:

```css
.box {
    transition: transform 0.5s;
}

.box:hover {
    transform: scale(1.2);
}
```

---

# ⭐ Useful Example

```css
.button {
    background-color: blue;
    transform: scale(1);
    transition: background-color 0.3s ease,
                transform 0.3s ease;
}

.button:hover {
    background-color: green;
    transform: scale(1.05);
}
```

Result:

```text
Hover
 ↓
color gradually changes
+
button gradually grows
```

---

# ⭐ Tips

* Transition needs a **change** to animate between states.
* `transition` itself doesn't create an animation; it smooths a change between two states.
* Put the transition on the **base element**.
* `s` = seconds, `ms` = milliseconds.

```text
1s = 1000ms
```

* Avoid extremely long transitions for normal UI interactions.
* `transform` is commonly paired with `transition` for smooth UI effects.

---

# ⚡ Quick Revision

```css
.box {
    transition-property: transform;
    transition-duration: 0.5s;
    transition-timing-function: ease;
    transition-delay: 0s;
}
```

Shorthand:

```css
.box {
    transition: transform 0.5s ease 0s;
}
```

### Main properties

| Property                     | Purpose       |
| ---------------------------- | ------------- |
| `transition-property`        | What changes  |
| `transition-duration`        | How long      |
| `transition-timing-function` | Speed pattern |
| `transition-delay`           | Waiting time  |

### 🧠 Remember

**Property → Duration → Timing → Delay**

```text
transition: transform 0.5s ease 0s;
              ↓         ↓     ↓    ↓
            WHAT      HOW LONG SPEED WAIT
```
