# HTML Cheat Sheet

## 1. Basic Page Structure

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Page Title</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>
  <h1>Hello, World!</h1>
  <script src="app.js"></script>
</body>
</html>
```

## 2. Text Elements

| Tag | Purpose |
|---|---|
| `<h1>` to `<h6>` | Headings (h1 is the most important) |
| `<p>` | Paragraph |
| `<br>` | Line break |
| `<hr>` | Horizontal divider |
| `<strong>` | Important text (bold) ||
| `<code>` | Inline code |
| `<pre>` | Preformatted text |
| `<span>` | Generic inline container |
| `<div>` | Generic block container |

## 3. Links and Images

```html
<a href="https://example.com">Visit site</a>
<a href="https://example.com" target="_blank" rel="noopener noreferrer">Open in new tab</a>
<a href="#section1">Jump to section</a>
<a href="mailto:me@example.com">Email me</a>
<a href="tel:+911234567890">Call me</a>

<img src="photo.jpg" alt="Describe the image" width="300" height="200">
```

## 4. Lists

```html
<!-- Unordered -->
<ul>
  <li>Java</li>
  <li>Spring Boot</li>
</ul>

<!-- Ordered -->
<ol>
  <li>First</li>
  <li>Second</li>
</ol>

<!-- Description list -->
<dl>
  <dt>HTML</dt>
  <dd>Structure of a web page</dd>
</dl>
```

## 5. Tables

```html
<table>
  <caption>Employees</caption>
  <thead>
    <tr>
      <th>Name</th>
      <th>Role</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Asha</td>
      <td>Developer</td>
    </tr>
  </tbody>
  <tfoot>
    <tr>
      <td>Total: 1</td>
    </tr>
  </tfoot>
</table>
```


## 6. Forms

```html
<form action="/submit" method="post">
  <label for="name">Name</label>
  <input type="text" id="name" name="name" placeholder="Your name" required>

  <label for="email">Email</label>
  <input type="email" id="email" name="email" required>

  <label for="pwd">Password</label>
  <input type="password" id="pwd" name="pwd" minlength="8">

  <label for="country">Country</label>
  <select id="country" name="country">
    <option value="in">India</option>
    <option value="us">USA</option>
  </select>

  <label for="msg">Message</label>
  <textarea id="msg" name="msg" rows="4" cols="30"></textarea>

  <input type="checkbox" id="agree" name="agree">
  <label for="agree">I agree</label>

  <input type="radio" id="m" name="gender" value="male">
  <label for="m">Male</label>
  <input type="radio" id="f" name="gender" value="female">
  <label for="f">Female</label>

  <button type="submit">Submit</button>
</form>
```

**Input types:** `text`, `password`, `email`, `number`, `tel`, `url`, `date`, `time`, `datetime-local`, `color`, `range`, `file`, `search`, `checkbox`, `radio`, `hidden`, `submit`, `reset`

| Attribute | Purpose |
|---|---|
| `name` | Key sent to the server |
| `value` | Default or current value |
| `placeholder` | Hint text |
| `required` | Field must be filled |
| `disabled` | Field cannot be used |
| `readonly` | Field cannot be edited |
| `min` / `max` | Range for numbers and dates |
| `minlength` / `maxlength` | Text length limits |
| `pattern` | Regex validation |
| `autofocus` | Focus on page load |

## 7. Semantic Layout

```html
<body>
  <header>Logo, title</header>
  <nav>Navigation links</nav>
  <main>
    <section>
      <article>Standalone content</article>
    </section>
    <aside>Sidebar or related info</aside>
  </main>
  <footer>Copyright, contact</footer>
</body>
```

| Tag | Use it for |
|---|---|
| `<header>` | Intro content or top of a page or section |
| `<nav>` | Main navigation links |
| `<main>` | Main content (only one per page) |
| `<section>` | A themed group of content |
| `<article>` | Self-contained piece (blog post, news item) |
| `<aside>` | Side content |
| `<footer>` | Bottom of a page or section |
| `<figure>` / `<figcaption>` | Image or diagram with a caption |
| `<details>` / `<summary>` | Expandable content |

## 8. Media

```html
<video src="movie.mp4" controls width="400" poster="thumb.jpg"></video>
<audio src="song.mp3" controls></audio>

<video controls>
  <source src="movie.webm" type="video/webm">
  <source src="movie.mp4" type="video/mp4">
  Your browser does not support video.
</video>

<iframe src="https://example.com" width="600" height="400" title="Embedded page"></iframe>
```

## 9. Global Attributes

| Attribute | Purpose |
|---|---|
| `id` | Unique identifier (one per page) |
| `class` | Group name for styling (reusable) |
| `style` | Inline CSS |
| `title` | Tooltip text |
| `hidden` | Hides the element |
| `lang` | Language of the content |
| `tabindex` | Keyboard focus order |
| `data-*` | Custom data, e.g. `data-user-id="5"` |
| `contenteditable` | Makes content editable |
| `aria-*` / `role` | Accessibility info |

## 10. Block vs Inline Elements

### The difference at a glance

| | Block | Inline | Inline-block |
|---|---|---|---|
| Starts on a new line | Yes | No | No |
| Width | Takes the full available width | Only as wide as its content | Only as wide as its content |
| `width` / `height` work | Yes | No | Yes |
| Top/bottom `margin` and `padding` | Yes | Not applied to layout | Yes |
| Left/right `margin` and `padding` | Yes | Yes | Yes |
| Can contain | Block and inline elements | Mostly other inline elements and text | Block and inline elements |

### Common block elements

`<div>`, `<p>`, `<h1>`-`<h6>`, `<ul>`, `<ol>`, `<li>`, `<dl>`, `<dt>`, `<dd>`, `<table>`, `<form>`, `<fieldset>`, `<header>`, `<nav>`, `<main>`, `<section>`, `<article>`, `<aside>`, `<footer>`, `<blockquote>`, `<pre>`, `<hr>`, `<figure>`, `<figcaption>`, `<address>`, `<details>`

### Common inline elements

`<span>`, `<a>`, `<strong>`, `<b>`, `<em>`, `<i>`, `<u>`, `<small>`, `<mark>`, `<code>`, `<kbd>`, `<samp>`, `<sub>`, `<sup>`, `<abbr>`, `<cite>`, `<q>`, `<time>`, `<label>`, `<br>`, `<img>`

### Inline-block (inline flow, but accepts width and height)

`<button>`, `<input>`, `<select>`, `<textarea>`, `<img>` (behaves like inline-block)

### See the difference

```html
<!-- Block elements: each one takes its own line -->
<div>Block 1</div>
<div>Block 2</div>
<p>Block 3</p>

<!-- Inline elements: sit side by side in the same line -->
<span>Inline 1</span>
<span>Inline 2</span>
<a href="#">Inline 3</a>

<!-- Inline text inside a block -->
<p>This is a <strong>bold</strong> word and a <em>slanted</em> word in one line.</p>
```

### Changing the behaviour with CSS `display`

```css
span   { display: block; }         /* now behaves like a block */
div    { display: inline; }        /* now behaves like inline */
a      { display: inline-block; }  /* inline flow, but width/height work */
.hide  { display: none; }          /* removed from the page layout completely */
```

| `display` value | Result |
|---|---|
| `block` | Full-width, new line |
| `inline` | Flows with text |
| `inline-block` | Flows with text, accepts width and height |
| `none` | Element is not shown and takes no space |
| `flex` | Block-level flex container (children laid out in a row or column) |
| `grid` | Block-level grid container |

### Nesting rules

- Block elements can contain other block and inline elements.
- Inline elements should contain only text and other inline elements.
- Do not put a block inside a `<p>`. Elements like `<div>` or `<ul>` inside `<p>` will close the paragraph automatically.
- `<a>` is inline, but in HTML5 it may wrap block content, such as a whole card, as long as no other link or button is inside it.

```html
<!-- Good -->
<div>
  <p>Hello <strong>world</strong></p>
</div>

<!-- Bad: div inside span -->
<span><div>Wrong</div></span>

<!-- Bad: div inside p -->
<p><div>Wrong</div></p>
```

### `<div>` vs `<span>`

| `<div>` | `<span>` |
|---|---|
| Block container | Inline container |
| Use for sections, layout, grouping blocks | Use for styling a part of the text |

## 11. HTML Entities

| Character | Entity |
|---|---|
| `<` | `&lt;` |
| `>` | `&gt;` |
| `&` | `&amp;` |
| `"` | `&quot;` |
| Non-breaking space | `&nbsp;` |
| © | `&copy;` |
| ₹ | `&#8377;` |

## 12. Useful `<head>` Tags

```html
<meta name="description" content="Short page summary for search engines">
<meta name="author" content="Your Name">
<link rel="icon" href="favicon.ico">
<style> body { margin: 0; } </style>
```

## 13. Script Loading

```html
<script src="a.js"></script>        <!-- blocks parsing until it runs -->
<script src="a.js" defer></script>  <!-- runs after HTML is parsed, in order -->
<script src="a.js" async></script>  <!-- runs as soon as downloaded, any order -->
```

## 14. Quick Reminders

- **Void elements** have no closing tag: `<br>`, `<hr>`, `<img>`, `<input>`, `<meta>`, `<link>`.
- **Comment:** `<!-- this is a comment -->`
- `id` is for one element, `class` is for many.
- HTML is structure, CSS is style, JavaScript is behaviour.
