# 🌐 Sigma Web Development — Tutorial #1

## Notes: 12:00 → End

### 1. 🌍 How Websites Work

```text
👤 Client
   ↓
🌐 Browser (Chrome)
   ↓ Request
🖥️ Server
   ↓ Response
🌐 Browser
   ↓
👤 Client
```

* **Client** → Device/user requesting information.
* **Browser** → Software used to access websites.
* **Server** → Receives requests, processes them, and sends responses.

---

### 2. 📤 Request & 📥 Response

* **Request** → Browser asks the server for a resource.
* **Response** → Server sends the requested resource/data back.

```text
Browser → Request → Server
Browser ← Response ← Server
```

The server may use a **database** while processing the request.

---

### 3. 🖥️ Server

A server is basically a computer/system that:

* Receives requests
* Processes requests
* Finds required data
* Sends responses

One server can handle requests from **many clients**.

---

### 4. 🔢 HTTP Status Codes

```text
200 → OK / Success ✅
404 → Not Found ❌
500 → Internal Server Error ❌
```

---

### 5. 🎨 Frontend & ⚙️ Backend

**Frontend** → What the user sees and interacts with.

**Backend** → Work happening behind the website.

```text
Frontend              Backend
HTML                  Server
CSS                   Database
JavaScript            Logic
```

---

### 6. 🏗️ HTML

**HTML = HyperText Markup Language**

Used to create the **structure** of a webpage.

Examples:

* Headings
* Paragraphs
* Images
* Links
* Buttons
* Videos

---

### 7. 🎨 CSS

**CSS = Cascading Style Sheets**

Used to **style/design** HTML.

Controls:

* Colors
* Fonts
* Size
* Spacing
* Layout
* Appearance

---

### 8. ⚡ JavaScript

JavaScript adds **logic and interactivity**.

Examples:

* Button actions
* Dynamic content
* Form interactions
* Changing webpage content

```text
HTML → Structure
CSS  → Styling
JS   → Behaviour
```

---

### 9. 🧩 Frontend Frameworks

Examples:

* **React**
* **Angular**
* **Next.js**

They help developers build modern web applications more efficiently.

---

### 10. 🧱 Website Analogy

Think of a website like a building:

```text
HTML       → Structure 🏗️
CSS        → Design 🎨
JavaScript → Behaviour ⚡
```

Easy way to remember:

> **HTML = What?**
> **CSS = How does it look?**
> **JS = What does it do?**

---

### 11. 🔍 Inspecting Websites

In Chrome:

```text
Right Click → Inspect
```

Shortcut:

```text
Ctrl + Shift + I
```

Developer Tools let you inspect:

* HTML
* CSS
* JavaScript
* Network requests
* Website elements

You can temporarily modify HTML/CSS using Inspect.

---

### 12. 🛠️ Learn by Building

You don't need to learn everything before making projects.

```text
Learn
 ↓
Build
 ↓
Make mistakes
 ↓
Fix mistakes
 ↓
Learn more
```

**Practice + projects are important for learning web development.**

---

## ⭐ Final Revision

```text
User
 ↓
Browser
 ↓ Request
Server
 ↓
Processing / Database
 ↓ Response
Browser
 ↓
Website
```

```text
HTML → Structure
CSS → Design
JS → Interactivity

200 → Success
404 → Not Found
500 → Server Error
```

**Chrome → Right Click → Inspect → Developer Tools**


# Video 2 — Your First HTML Website

## 1. Basic Website Structure

A basic website uses three main files:

```text
index.html   → Structure
style.css    → Styling
script.js    → Functionality
```

* **HTML** → creates the structure/content.
* **CSS** → controls appearance/design.
* **JavaScript** → adds functionality/behavior.

---

## 2. Creating an HTML Page

Basic HTML structure:

```html
<!DOCTYPE html>
<html>
<head>
    <title>My First Website</title>
</head>

<body>
    <h1>My First Website</h1>
</body>
</html>
```

### Important parts

* `<!DOCTYPE html>` → tells the browser the document is HTML5.
* `<html>` → root element.
* `<head>` → contains page information/metadata.
* `<title>` → title shown in the browser tab.
* `<body>` → contains the visible webpage content.
* `<h1>` → main heading.

---

## 3. Linking CSS with HTML

CSS is written separately in `style.css`.

Example:

```css
body {
    background-color: red;
    color: white;
}
```

Connect it to HTML using:

```html
<link rel="stylesheet" href="style.css">
```

Usually placed inside `<head>`:

```html
<head>
    <title>My First Website</title>
    <link rel="stylesheet" href="style.css">
</head>
```

### Flow

```text
index.html
    ↓
style.css
    ↓
Website appearance
```

Without the `<link>` tag, the external CSS file will not style the HTML page.

---

## 4. Linking JavaScript with HTML

JavaScript is used to add functionality.

`script.js`:

```javascript
alert("Hello World");
```

Connect it to HTML:

```html
<script src="script.js"></script>
```

A common placement is before `</body>`:

```html
<body>

    <h1>My First Website</h1>

    <script src="script.js"></script>
</body>
```

### Flow

```text
index.html
    ↓
script.js
    ↓
Website functionality
```

---

## 5. Emmet

**Emmet** helps write HTML/CSS faster using short abbreviations.

Instead of writing long HTML structures manually, Emmet can generate them automatically.

**Purpose:** faster and easier coding.

---

## 6. Client–Server Interaction

Websites work using communication between a **client** and a **server**.

### Client

The device/browser that requests something.

Example:

```text
Your computer + web browser
```

### Server

A computer/system that receives requests and provides the required response.

### Basic process

```text
Client
  │
  │ Request
  ↓
Server
  │
  │ Response
  ↓
Client
```

### Example

When you visit a website:

```text
Browser
   ↓
Request
   ↓
Website Server
   ↓
Response
   ↓
Website displayed in Browser
```

The same basic client-server concept applies when interacting with an online store, such as requesting information about a product.

---

## 7. Web Development Learning Order

The basic progression introduced is:

```text
HTML
  ↓
CSS
  ↓
JavaScript
```

* **HTML** → structure
* **CSS** → design
* **JavaScript** → functionality

---

# ⭐ Quick Revision

* `index.html` → website structure
* `style.css` → website styling
* `script.js` → website functionality
* `<link rel="stylesheet" href="style.css">` → connects CSS
* `<script src="script.js"></script>` → connects JavaScript
* **Emmet** → faster HTML/CSS writing
* **Client** → sends request
* **Server** → processes/responds
* Basic flow → **Client → Request → Server → Response → Client**
* Learning order → **HTML → CSS → JavaScript**
