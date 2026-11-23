# CSS Cheat Sheet

## 1. Ways to Add CSS

```html
<!-- External (best) -->
<link rel="stylesheet" href="style.css">

<!-- Internal -->
<style>
  p { color: blue; }
</style>

<!-- Inline (avoid) -->
<p style="color: blue;">Text</p>
```

## 2. Basic Syntax and Selectors

```css
selector {
  property: value;
}
```

| Selector | Example | Selects |
|---|---|---|
| Element | `p` | All `<p>` tags |
| Class | `.card` | Elements with `class="card"` |
| ID | `#header` | The element with `id="header"` |
| Universal | `*` | Everything |
| Group | `h1, h2, h3` | All of them |
| Descendant | `nav a` | Any `<a>` inside `<nav>` |
| Child | `ul > li` | Direct `<li>` children of `<ul>` |
| Adjacent sibling | `h1 + p` | `<p>` right after `<h1>` |
| Attribute | `input[type="text"]` | Inputs with that attribute |
| Pseudo-class | `a:hover`, `li:first-child`, `li:nth-child(2)` | An element in a state or position |
| Pseudo-element | `p::first-line`, `div::before`, `div::after` | A part of an element |

## 3. Box Model

Every element is a box made of four layers, from inside to outside:

**content → padding → border → margin**

```css
.box {
  width: 300px;
  height: 150px;
  padding: 20px;              /* space inside the border */
  border: 2px solid black;    /* the edge */
  margin: 10px;               /* space outside the border */
  box-sizing: border-box;     /* width includes padding + border */
}

/* Shorthand order: top right bottom left (clockwise) */
margin: 10px 20px 10px 20px;
margin: 10px 20px;            /* top/bottom  left/right */
margin: 0 auto;               /* centers a block horizontally (needs a width) */
```

**Always add this reset:**

```css
*, *::before, *::after {
  box-sizing: border-box;
}
```

| `box-sizing` | Total width |
|---|---|
| `content-box` (default) | width + padding + border |
| `border-box` | width (padding and border are included) |

## 4. Display: Block vs Inline

| | Block | Inline | Inline-block |
|---|---|---|---|
| Starts on a new line | Yes | No | No |
| Width | Full available width | Only its content | Only its content |
| `width` / `height` work | Yes | No | Yes |
| Vertical margin/padding | Yes | Not applied to layout | Yes |

```css
span  { display: block; }         /* acts like a block */
div   { display: inline; }        /* acts like inline */
a     { display: inline-block; }  /* inline flow, but width/height work */
.hide { display: none; }          /* removed from layout */
```

| `display` value | Result |
|---|---|
| `block` | Full-width, new line |
| `inline` | Flows with text |
| `inline-block` | Flows with text, accepts width and height |
| `none` | Not shown and takes no space |
| `flex` | Flex container |
| `grid` | Grid container |

## 5. Positioning

```css
.box {
  position: static;    /* default, normal flow */
  position: relative;  /* offset from its own normal spot */
  position: absolute;  /* positioned against nearest positioned ancestor */
  position: fixed;     /* stays fixed to the viewport */
  position: sticky;    /* normal until scroll point, then sticks */
  top: 10px;
  left: 20px;
  z-index: 10;         /* stacking order (higher = on top) */
}
```

| Value | Behaviour |
|---|---|
| `relative` | Moves relative to where it would normally be. It still keeps its original space. |
| `absolute` | Removed from the flow. Positions against the nearest ancestor that has `position` other than `static`, else the page. |
| `fixed` | Positions against the browser window. It stays during scroll. |
| `sticky` | Acts `relative` until you scroll past a threshold, then acts `fixed`. |

**Most common pattern: absolute child inside a relative parent**

```css
.parent {
  position: relative;
}
.badge {
  position: absolute;
  top: 0;
  right: 0;
}
```

**Sticky header:**

```css
header {
  position: sticky;
  top: 0;
  z-index: 100;
}
```

## 6. Common Structural Classes (layout)

```css
.container {
  max-width: 1100px;
  margin: 0 auto;
  padding: 0 16px;
}

.row {
  display: flex;
  flex-wrap: wrap;
  gap: 16px;
}

.col {
  flex: 1;
}

.grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 16px;
}

.navbar {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 12px 24px;
}

.sidebar { width: 250px; }
.main    { flex: 1; }
.footer  { padding: 24px; text-align: center; }

.clearfix::after {
  content: "";
  display: block;
  clear: both;
}

.hidden { display: none; }
```

## 7. Common Styling Classes

```css
/* Text */
.text-center  { text-align: center; }
.text-right   { text-align: right; }
.bold         { font-weight: bold; }
.uppercase    { text-transform: uppercase; }
.muted        { color: #6b7280; }

/* Colors */
.bg-dark      { background: #111827; color: white; }
.bg-light     { background: #f3f4f6; }
.primary      { color: #2563eb; }

/* Spacing */
.m-0   { margin: 0; }
.mt-2  { margin-top: 16px; }
.p-2   { padding: 16px; }

/* Components */
.btn {
  display: inline-block;
  padding: 10px 20px;
  background: #2563eb;
  color: white;
  border: none;
  border-radius: 6px;
  cursor: pointer;
  text-decoration: none;
}
.btn:hover { background: #1d4ed8; }

.card {
  background: white;
  border: 1px solid #e5e7eb;
  border-radius: 8px;
  padding: 16px;
  box-shadow: 0 2px 6px rgba(0, 0, 0, 0.1);
}

.rounded { border-radius: 8px; }
.circle  { border-radius: 50%; }
```

## 8. Specificity (which rule wins)

When rules conflict, the more specific selector wins. If equal, the **later** one wins.

| Selector type | Weight | Example |
|---|---|---|
| Inline style | 1000 | `style="..."` |
| ID | 100 | `#header` |
| Class, attribute, pseudo-class | 10 | `.card`, `[type="text"]`, `:hover` |
| Element, pseudo-element | 1 | `p`, `::before` |
| Universal `*` | 0 | `*` |

```css
p            { color: black; }   /* 1   */
.note        { color: blue; }    /* 10  */
p.note       { color: green; }   /* 11  */
#intro       { color: red; }     /* 100 */
#intro p.note { color: orange; } /* 111 */
```

- `!important` beats everything, so avoid it.
- Prefer classes. Avoid IDs for styling.
- Keep selectors short.

## 9. Units and Colors

| Unit | Meaning |
|---|---|
| `px` | Fixed pixels |
| `%` | Percent of the parent |
| `em` | Relative to the parent's font size |
| `rem` | Relative to the root (`html`) font size |
| `vw` / `vh` | 1% of viewport width / height |
| `fr` | A fraction of the free space (Grid) |

```css
color: red;                      /* name */
color: #2563eb;                  /* hex */
color: rgb(37, 99, 235);         /* rgb */
color: rgba(0, 0, 0, 0.5);       /* with transparency */
color: hsl(220, 80%, 50%);       /* hsl */
```

## 10. Typography

```css
body {
  font-family: "Segoe UI", Arial, sans-serif;
  font-size: 16px;
  font-weight: 400;      /* 100-900 */
  line-height: 1.6;
  color: #111827;
}

h1 {
  font-size: 2rem;
  text-align: center;
  letter-spacing: 1px;
  text-decoration: underline;
  text-transform: capitalize;
}

a { text-decoration: none; }
```

## 11. Flexbox (one dimension: row or column)

```css
.container {
  display: flex;
  flex-direction: row;            /* row | column */
  justify-content: space-between; /* main axis */
  align-items: center;            /* cross axis */
  flex-wrap: wrap;
  gap: 16px;
}

.item {
  flex: 1;          /* grow equally */
  flex: 0 0 200px;  /* fixed 200px, no grow, no shrink */
}
```

| Property | Common values |
|---|---|
| `justify-content` | `flex-start`, `center`, `flex-end`, `space-between`, `space-around`, `space-evenly` |
| `align-items` | `stretch`, `flex-start`, `center`, `flex-end` |
| `flex-direction` | `row`, `row-reverse`, `column`, `column-reverse` |

**Center anything perfectly:**

```css
.center {
  display: flex;
  justify-content: center;
  align-items: center;
  min-height: 100vh;
}
```

## 12. Grid (two dimensions: rows and columns)

```css
.grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);   /* 3 equal columns */
  grid-template-columns: 250px 1fr;        /* sidebar + content */
  gap: 16px;
}

.wide {
  grid-column: span 2;   /* take 2 columns */
}

/* Responsive grid without media queries */
.cards {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 16px;
}
```

| Use | When |
|---|---|
| Flexbox | Nav bars, rows of items, centering, one direction |
| Grid | Page layouts, card galleries, rows and columns together |

## 13. Responsive Design and Media Queries

Make sure the viewport meta tag is in your HTML `<head>` (see the HTML cheat sheet), otherwise phones will not scale the page.

```css
/* Mobile first: base styles are for small screens */
.cards {
  display: grid;
  grid-template-columns: 1fr;
}

/* Tablet and up */
@media (min-width: 768px) {
  .cards { grid-template-columns: repeat(2, 1fr); }
}

/* Desktop and up */
@media (min-width: 1024px) {
  .cards { grid-template-columns: repeat(3, 1fr); }
}

/* Other useful queries */
@media (max-width: 600px) { .sidebar { display: none; } }
@media (prefers-color-scheme: dark) { body { background: #111; color: #eee; } }
@media print { nav { display: none; } }
```

| Common breakpoints | Device |
|---|---|
| `480px` | Small phones |
| `768px` | Tablets |
| `1024px` | Laptops |
| `1200px` | Large desktops |

Make images responsive:

```css
img {
  max-width: 100%;
  height: auto;
}
```

## 14. Backgrounds, Borders and Shadows

```css
.hero {
  background-color: #f3f4f6;
  background-image: url("hero.jpg");
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
}

.gradient {
  background: linear-gradient(to right, #2563eb, #7c3aed);
}

.box {
  border: 1px solid #ccc;        /* width style color */
  border-radius: 8px;
  box-shadow: 0 2px 6px rgba(0, 0, 0, 0.15);  /* x y blur color */
  opacity: 0.9;
}
```

## 15. Transitions and Hover Effects

```css
.btn {
  background: #2563eb;
  transition: all 0.3s ease;
}
.btn:hover {
  background: #1d4ed8;
  transform: translateY(-2px) scale(1.05);
}
```

Common transforms: `translate()`, `rotate(45deg)`, `scale(1.2)`.

## 16. CSS Variables

```css
:root {
  --primary: #2563eb;
  --radius: 8px;
  --space: 16px;
}

.btn {
  background: var(--primary);
  border-radius: var(--radius);
  padding: var(--space);
}
```

## 17. Overflow and Visibility

```css
.box {
  overflow: hidden;    /* cut off extra content */
  overflow: auto;      /* scrollbar only if needed */
  overflow-y: scroll;
  text-overflow: ellipsis;   /* with white-space: nowrap; overflow: hidden; */
  display: none;       /* removed completely */
  visibility: hidden;  /* invisible, still takes space */
}
```

