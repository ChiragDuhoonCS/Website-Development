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


## Video 3 — Basic Structure of an HTML Website

### 1. Basic HTML Structure

A basic HTML document:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <title>My Website</title>
</head>
<body>

</body>
</html>
```

### Important tags

* `<!DOCTYPE html>` → declares HTML5 document.
* `<html>` → root element of the page.
* `<head>` → contains information about the page.
* `<body>` → contains the visible content.
* `<title>` → page title shown in the browser tab.

### `lang` attribute

```html
<html lang="en">
```

* `lang="en"` tells browsers/search engines that the page is in English.
* Helps with **accessibility and SEO**.

### Pair vs self-closing/void tags

**Pair/container tag:**

```html
<title>My Website</title>
```

Has opening + closing tags.

**Void/self-closing type tag:**

```html
<meta charset="UTF-8">
```

Does not need a closing tag.

---

### 2. `<head>` Section

The `<head>` contains information/metadata about the webpage, such as:

* `<title>`
* `<meta>`
* CSS links
* JavaScript links
* SEO-related information

### Meta description

```html
<meta name="description" content="This is my website">
```

* Describes the webpage.
* Search engines can use this information when displaying search results.

### Title and SEO

```html
<title>My Website</title>
```

* The title describes the page.
* Important for **SEO/search engines**.
* A good title should accurately represent the page's content.

---

### 3. `<body>` Section

```html
<body>
    <h1>My Website</h1>
    <p>This is my webpage.</p>
</body>
```

Everything inside `<body>` is the main content displayed on the webpage.

### Basic structure

```text
<html>
 ├── <head>
 │    ├── <title>
 │    └── <meta>
 │
 └── <body>
      └── Visible content
```

The video also reinforces that **CSS and JavaScript** are used with HTML to add styling and functionality. ([Video Highlight][1])

---

### 4. HTML Attributes

An **attribute** provides additional information about an HTML element.

Example:

```html
<html lang="en">
```

* `lang` → attribute
* `"en"` → attribute value

General syntax:

```html
<tag attribute="value">
```

---

### 5. Mobile Preview Tip

The video shows a quick way to preview a webpage on a mobile device while developing.

**Main idea:** test webpages on different screen sizes instead of checking only on a desktop.

---

### ⭐ Quick Revision

* `<!DOCTYPE html>` → HTML5 declaration
* `<html>` → root
* `<head>` → metadata/page information
* `<body>` → visible content
* `<title>` → browser title + important for SEO
* `<meta name="description">` → page description
* `lang="en"` → specifies page language
* **Attribute:** `name="value"`
* HTML structure → **HTML → Head + Body** ([Video Highlight][1])

# Video 4 — Headings, Paragraphs & Links

## 1. Headings

HTML provides **6 heading levels**:

```html
<h1>Heading 1</h1>
<h2>Heading 2</h2>
<h3>Heading 3</h3>
<h4>Heading 4</h4>
<h5>Heading 5</h5>
<h6>Heading 6</h6>
```

* `<h1>` → highest/main heading.
* `<h6>` → lowest heading level.
* Headings create a **hierarchy** for webpage content.
* In practical websites, `<h1>`, `<h2>`, and `<h3>` are commonly enough for many sections.

Example:

```html
<h1>My Bookmarks</h1>

<h2>Primary Bookmarks</h2>
<h2>Secondary Bookmarks</h2>
```

Headings help both users and search engines understand the structure of the page. ([Video Highlight][2])

---

## 2. Paragraphs

Paragraphs use:

```html
<p>This is a paragraph.</p>
```

Multiple paragraphs:

```html
<p>First paragraph.</p>
<p>Second paragraph.</p>
```

### Lorem Ipsum

**Lorem Ipsum** is dummy/placeholder text used while designing a webpage before the real content is available.

Example:

```text
lorem
```

Emmet can generate dummy text quickly.

---

## 3. HTML Attributes

Attributes provide additional information to HTML elements.

Example:

```html
<html lang="en">
```

Another example:

```html
<p style="background-color: red;">
    Hello
</p>
```

Here:

* `style` → attribute
* `background-color: red;` → attribute value

Inline styling can be useful for quick changes, but shouldn't be overused in larger projects because it becomes harder to maintain. ([Video Highlight][2])

---

## 4. Anchor / Link Tag

Links are created using the `<a>` tag.

```html
<a href="https://www.google.com">Google</a>
```

### Important

```text
<a>        → anchor tag
href       → destination
Google     → clickable text
```

`href` is required to specify where the link should go.

---

## 5. Opening a Link in a New Tab

Use:

```html
<a href="https://www.google.com" target="_blank">
    Google
</a>
```

* `target="_blank"` → opens the link in a new tab/window.

---

## 6. Visited Links

Browsers normally show:

```text
Unvisited → Blue
Visited   → Purple
```

This helps indicate that a link has already been visited.

---

## 7. Bookmark Manager

The video creates a simple **bookmark manager** using headings and links.

Example:

```html
<h1>My Bookmarks</h1>

<h2>Primary Bookmarks</h2>

<a href="https://www.google.com">Google</a>
<a href="https://www.facebook.com">Facebook</a>

<h2>Secondary Bookmarks</h2>

<a href="https://www.wikipedia.org">Wikipedia</a>
<a href="https://stackoverflow.com">Stack Overflow</a>
```

The links act as bookmarks for frequently used websites.

For proper organization, lists are later preferable to placing many bookmarks inside separate paragraphs. ([Video Highlight][2])

---

### ⭐ Quick Revision

* `<h1>` → main heading
* `<h1>` to `<h6>` → heading hierarchy
* `<p>` → paragraph
* **Lorem Ipsum** → placeholder text
* `<a>` → creates link
* `href` → link destination
* `target="_blank"` → opens link in new tab
* `style` → inline CSS
* Bookmark manager → headings + links ([Video Highlight][2])

# Video 5 — Images, Lists & Tables

## 1. Images in HTML

Images are added using:

```html
<img src="image.jpg" alt="Description">
```

### Important attributes

| Attribute | Purpose             |
| --------- | ------------------- |
| `src`     | Image location/path |
| `alt`     | Alternative text    |

### `src`

Specifies where the image comes from.

```html
<img src="train.jpg">
```

It can point to an image file or image URL.

### `alt`

Describes the image:

```html
<img src="train.jpg" alt="A train">
```

If the image cannot load, the **alt text can be displayed instead**.

---

## 2. Image Width & Height

```html
<img src="train.jpg"
     alt="A train"
     width="500"
     height="300">
```

* `width` → image width.
* `height` → image height.
* Values are generally given as pixel values when used this way; no `px` is written in the HTML attribute.

### Aspect Ratio

When changing image dimensions, maintain the **aspect ratio** so the image doesn't look stretched or distorted.

The video also explains that CSS is generally preferred for controlling image dimensions rather than relying heavily on HTML presentation attributes. Setting an appropriate dimension can also help maintain layout stability while an image loads. ([Video Highlight][3])

---

## 3. `style` Attribute

The `style` attribute can be used with HTML elements.

Example:

```html
<img src="train.jpg" style="width: 500px;">
```

It can be used for quick styling, although CSS is better for managing styling systematically.

---

# 4. HTML Tables

Tables display **structured/tabular data**.

Basic structure:

```html
<table>
    <tr>
        <th>Name</th>
        <th>Language</th>
    </tr>

    <tr>
        <td>Harry</td>
        <td>Python</td>
    </tr>
</table>
```

### Important tags

| Tag       | Meaning            |
| --------- | ------------------ |
| `<table>` | Creates table      |
| `<tr>`    | Table row          |
| `<th>`    | Table heading/cell |
| `<td>`    | Table data cell    |

### Structure

```text
<table>
   ├── <tr> → row
   │    ├── <th> → heading
   │    └── <th> → heading
   │
   └── <tr> → row
        ├── <td> → data
        └── <td> → data
```

---

# 5. `rowspan`

`rowspan` makes a cell span **multiple rows vertically**.

```html
<td rowspan="2">Harry</td>
```

```text
┌────────┬──────┐
│ Harry  │ A    │
│        ├──────┤
│        │ B    │
└────────┴──────┘
```

`rowspan="2"` → cell occupies 2 rows.

---

# 6. `colspan`

`colspan` makes a cell span **multiple columns horizontally**.

```html
<td colspan="2">Harry</td>
```

`colspan="2"` → cell occupies 2 columns.

```text
┌────────────────┐
│     Harry      │
└────────────────┘
```

### Remember

```text
rowspan  → rows → vertical
colspan  → columns → horizontal
```

([Video Highlight][3])

---

# 7. Table Caption

`<caption>` adds a title/caption to a table.

```html
<table>
    <caption>Student Details</caption>

    ...
</table>
```

Example:

```html
<caption>Employee Details</caption>
```

---

# 8. Table Sections

Tables can be divided into:

```html
<thead>
    ...
</thead>

<tbody>
    ...
</tbody>

<tfoot>
    ...
</tfoot>
```

### Purpose

* `<thead>` → table header section
* `<tbody>` → main table data
* `<tfoot>` → table footer

Grouping table content also makes it easier to target sections with CSS. ([Video Highlight][3])

---

# 9. HTML Lists

HTML has **3 main types of lists**:

```text
1. Ordered list
2. Unordered list
3. Definition list
```

---

## 10. Unordered List

Uses `<ul>`.

```html
<ul>
    <li>Apple</li>
    <li>Banana</li>
    <li>Mango</li>
</ul>
```

* `<ul>` → unordered list
* `<li>` → list item

Output uses bullets.

### Changing bullet type

The `type` attribute can change the bullet style:

```html
<ul type="square">
    <li>Apple</li>
    <li>Banana</li>
</ul>
```

Other examples shown include bullet styles such as `circle`.

---

# 11. Ordered List

Uses `<ol>`.

```html
<ol>
    <li>HTML</li>
    <li>CSS</li>
    <li>JavaScript</li>
</ol>
```

Output:

```text
1. HTML
2. CSS
3. JavaScript
```

Ordered lists can use different numbering styles with the `type` attribute, including letters and Roman numerals.

Example:

```html
<ol type="A">
    <li>HTML</li>
    <li>CSS</li>
</ol>
```

---

# 12. Definition List

Uses:

* `<dl>` → definition list
* `<dt>` → definition term
* `<dd>` → term description

Example:

```html
<dl>
    <dt>HTML</dt>
    <dd>HyperText Markup Language</dd>

    <dt>CSS</dt>
    <dd>Cascading Style Sheets</dd>
</dl>
```

Definition lists are less commonly used than ordered/unordered lists but are useful for **terms and their definitions**. ([Video Highlight][3])

---

## ⭐ Quick Revision

### Images

```html
<img src="..." alt="..." width="..." height="...">
```

* `src` → image source
* `alt` → alternative description
* Maintain aspect ratio.

### Tables

```text
<table> → table
<tr>    → row
<th>    → heading
<td>    → data
```

* `rowspan` → merge/span rows vertically
* `colspan` → merge/span columns horizontally
* `<caption>` → table title
* `<thead>` / `<tbody>` / `<tfoot>` → table sections

### Lists

```text
<ul> → unordered/bullets
<ol> → ordered/numbers
<dl> → definitions
<li> → list item
<dt> → definition term
<dd> → definition
```

These are the core concepts from Videos **3, 4, and 5**, with setup/promotion content removed as requested. ([Video Highlight][1])

[1]: https://videohighlight.com/v/BGeDBfCIqas?aiFormatted=false&language=en&mediaType=youtube&summaryId=QijSrVnASUG4MPjJgGlo&summaryType=compressed&utm_source=chatgpt.com "Basic Structure of an HTML Website | Sigma Web Development Course - Tutorial #3 | YouTube Video Summary | Video Highlight"
[2]: https://videohighlight.com/v/nXba2-mgn1k?view=defaultSummary "Heading, Paragraphs and Links | Sigma Web Development Course - Tutorial #4 | YouTube Video Summary | Video Highlight"
[3]: https://videohighlight.com/v/1BsVhumGlNc?aiFormatted=false&language=en&mediaType=youtube&summaryId=q0gPd5dyRMeYEh6ZRpii&summaryType=compressed "Image, Lists, and Tables in HTML | Sigma Web Development Course - Tutorial #5 | YouTube Video Summary | Video Highlight"
