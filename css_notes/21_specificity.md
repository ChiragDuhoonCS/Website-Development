# Video 20 — CSS Specificity

## 1. What is Specificity?

**Specificity** determines **which CSS rule is applied** when multiple CSS rules target the same element.

Example:

```html
<p id="para" class="text">Hello</p>
```

```css
p {
    color: blue;
}

.text {
    color: red;
}

#para {
    color: green;
}
```

All 3 selectors target the same `<p>`, but the text becomes **green** because the ID selector has higher specificity.

---

# 2. Specificity Order

From **lower → higher** specificity:

```text
Universal selector
      ↓
Element selector
      ↓
Class / Attribute / Pseudo-class
      ↓
ID selector
      ↓
Inline CSS
      ↓
!important
```

### Easy memory 💡

```text
* → tag → class → ID → inline
```

---

# 3. Universal Selector

```css
* {
    color: red;
}
```

Very low specificity.

---

# 4. Element Selector

```css
p {
    color: blue;
}
```

Targets all `<p>` elements.

Element selectors have higher specificity than `*`.

---

# 5. Class Selector

```css
.text {
    color: green;
}
```

Class selectors have higher specificity than element selectors.

---

# 6. ID Selector

```css
#para {
    color: yellow;
}
```

ID selectors have higher specificity than classes.

---

# 7. Inline CSS

```html
<p style="color: pink;">
    Hello
</p>
```

Inline styling has higher priority than normal selector rules.

---

# 8. `!important`

`!important` gives a declaration very high priority.

```css
p {
    color: red !important;
}
```

It can override normal declarations with lower priority.

### ⚠️ Tip

Don't use `!important` unnecessarily.

It can make CSS difficult to debug and override later.

---

# 9. Specificity Calculation

Specificity can be thought of using four categories:

```text
Inline | ID | Class/Attribute/Pseudo-class | Element
```

Represented as:

```text
(a, b, c, d)
```

### Examples

```css
p { }
```

```text
(0, 0, 0, 1)
```

```css
.text { }
```

```text
(0, 0, 1, 0)
```

```css
#para { }
```

```text
(0, 1, 0, 0)
```

---

# 10. Multiple Selectors

Example:

```css
p.text {
    color: red;
}
```

This contains:

```text
p      → element
.text  → class
```

So its specificity is higher than just:

```css
p {
    color: blue;
}
```

---

## 11. Example

HTML:

```html
<p id="para" class="text">Hello</p>
```

CSS:

```css
p {
    color: blue;
}

.text {
    color: red;
}

#para {
    color: green;
}
```

All rules match.

Specificity:

```text
p       → lower
.text   → higher
#para   → highest
```

Therefore:

```text
Result → green
```

---

# 12. Same Specificity → Later Rule Wins

If two selectors have the **same specificity**, the rule that appears **later** generally wins.

```css
.text {
    color: red;
}

.text {
    color: blue;
}
```

Result:

```text
blue
```

because the second `.text` rule comes later.

### Tip 💡

Think:

```text
Higher specificity → wins
Same specificity → later rule wins
```

---

# ⭐ Specificity Tips

### Remember this order:

```text
* 
↓
element
↓
class / attribute / pseudo-class
↓
ID
↓
inline
```

### Don't confuse:

```css
p { }        /* element */
.text { }    /* class */
#text { }    /* ID */
```

* `.` → class
* `#` → ID

### Important

Specificity is **not simply about how many characters or rules you write**.

For example:

```css
#box {
    color: red;
}
```

beats a selector containing several element selectors because an ID has much greater specificity.

---

# ⚡ Quick Revision

```text
CSS Specificity
      ↓
Determines which conflicting rule wins

*       → lowest
element
class
attribute
pseudo-class
ID
inline  → higher
!important → special highest priority
```

### Golden rule 🧠

> **When CSS rules conflict: compare specificity. If specificity is equal, the later rule wins.**
