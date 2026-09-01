# CSS Animations — Tutorial #46

## 1. What are CSS Animations?

CSS animations allow an element to **change styles automatically over time**.

Unlike `transition`, an animation can run through **multiple stages** using `@keyframes`.

Basic structure:

```css
.box {
    animation: myAnimation 3s;
}

@keyframes myAnimation {
    from {
        /* starting style */
    }

    to {
        /* ending style */
    }
}
```

---

## 2. `@keyframes`

`@keyframes` defines **what happens during the animation**.

```css
@keyframes example {
    from {
        background-color: red;
    }

    to {
        background-color: blue;
    }
}
```

```text
from → starting state
  ↓
 animation
  ↓
to → ending state
```

---

## 3. Applying an Animation

Defining `@keyframes` alone doesn't run the animation.

You apply it using:

```css
.box {
    animation-name: example;
    animation-duration: 2s;
}
```

Or shorthand:

```css
.box {
    animation: example 2s;
}
```

---

# 4. Animation Duration

Controls how long one animation cycle takes.

```css
.box {
    animation-duration: 3s;
}
```

Examples:

```text
1s   → 1 second
500ms → 0.5 second
3s   → 3 seconds
```

---

# 5. Using Percentages in `@keyframes`

Instead of only `from` and `to`, you can define multiple stages.

```css
@keyframes example {
    0% {
        transform: translateX(0);
    }

    50% {
        transform: translateX(100px);
    }

    100% {
        transform: translateX(200px);
    }
}
```

This gives you much more control over the animation.

```text
0%       → starting point
50%      → middle
100%     → ending point
```

---

# 6. `animation-iteration-count`

Controls **how many times** the animation runs.

```css
.box {
    animation-iteration-count: 3;
}
```

The animation runs 3 times.

For infinite repetition:

```css
.box {
    animation-iteration-count: infinite;
}
```

### Example

```css
.box {
    animation: move 2s infinite;
}
```

---

# 7. `animation-timing-function`

Controls the **speed pattern** of the animation.

```css
.box {
    animation-timing-function: ease;
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

Same basic idea as transitions.

---

# 8. `animation-delay`

Specifies how long to wait before the animation starts.

```css
.box {
    animation-delay: 2s;
}
```

```text
Element appears
      ↓
   wait 2s
      ↓
animation starts
```

---

# 9. `animation-direction`

Controls the direction of repeated animation.

```css
.box {
    animation-direction: alternate;
}
```

Common values:

```text
normal
reverse
alternate
alternate-reverse
```

### `normal`

Runs:

```text
0% → 100%
```

### `reverse`

Runs:

```text
100% → 0%
```

### `alternate`

Runs:

```text
0% → 100%
100% → 0%
0% → 100%
...
```

Useful with:

```css
animation-iteration-count: infinite;
```

---

# 10. `animation-fill-mode`

Controls the styles applied **before and/or after** the animation.

Common values:

```text
none
forwards
backwards
both
```

### `forwards`

The element keeps the styles from the **final keyframe** after the animation finishes.

```css
.box {
    animation-fill-mode: forwards;
}
```

### `backwards`

Applies the styles from the first relevant keyframe during the delay period.

### `both`

Combines `forwards` and `backwards`.

---

# 11. `animation-play-state`

Controls whether an animation is **running or paused**.

```css
.box {
    animation-play-state: paused;
}
```

To run:

```css
.box {
    animation-play-state: running;
}
```

A common use is pausing an animation on hover or through JavaScript.

---

# 12. Animation Shorthand

Instead of writing everything separately:

```css
.box {
    animation-name: move;
    animation-duration: 2s;
    animation-timing-function: ease;
    animation-delay: 1s;
    animation-iteration-count: infinite;
    animation-direction: alternate;
}
```

You can use:

```css
.box {
    animation: move 2s ease 1s infinite alternate;
}
```

### Important values to remember:

```text
name
duration
timing-function
delay
iteration-count
direction
```

---

# 13. Complete Example

```css
.box {
    width: 100px;
    height: 100px;
    background: red;

    animation: move 3s ease-in-out infinite alternate;
}

@keyframes move {
    0% {
        transform: translateX(0);
    }

    100% {
        transform: translateX(300px);
    }
}
```

### What happens?

```text
Box
 ↓
moves from 0px → 300px
 ↓
takes 3 seconds
 ↓
moves back
 ↓
repeats forever
```

---

# ⭐ Animation vs Transition

| Transition                          | Animation             |
| ----------------------------------- | --------------------- |
| Usually triggered by a change/state | Can run automatically |
| Commonly uses `:hover`              | Uses `@keyframes`     |
| Generally from one state to another | Can have many stages  |
| No `@keyframes` required            | Uses `@keyframes`     |

### Example

**Transition:**

```css
.box {
    transition: transform 0.5s;
}

.box:hover {
    transform: scale(1.2);
}
```

**Animation:**

```css
.box {
    animation: move 2s infinite;
}

@keyframes move {
    from {
        transform: translateX(0);
    }

    to {
        transform: translateX(200px);
    }
}
```

---

# 💡 Tips

* `@keyframes` defines the animation stages.
* `animation-name` connects the element to the keyframes.
* `animation-duration` is important—without a positive duration, the animation won't visibly progress.
* Use `%` keyframes when you need **more than just start/end states**.
* `infinite` is useful for loaders, bouncing effects, etc., but don't overuse it.
* `transform` is commonly used inside animations for movement, rotation and scaling.

---

# ⚡ Quick Revision

```css
.box {
    animation: move 2s ease infinite alternate;
}

@keyframes move {
    0% {
        transform: translateX(0);
    }

    50% {
        transform: translateX(100px);
    }

    100% {
        transform: translateX(200px);
    }
}
```

### Main properties

```text
animation-name           → which animation
animation-duration       → how long
animation-timing-function → speed pattern
animation-delay          → waiting time
animation-iteration-count → repetitions
animation-direction      → direction
animation-fill-mode      → styles before/after
animation-play-state     → running/paused
```

### 🧠 Remember

**`@keyframes` = animation blueprint**

```text
@keyframes
   ↓
Define stages
   ↓
animation property
   ↓
Run the animation
```
