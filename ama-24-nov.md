
# Questions and Answers

## 1. What is CSS specificity?
CSS specificity determines which CSS rule gets applied when multiple selectors target the same HTML element.

Priority order:
1. Inline CSS
2. ID selector
3. Class selector
4. Element selector

## 2. What is the difference between `add()` and `update()` in Python?
- `add()` adds a single element to a set.
- `update()` adds multiple elements from an iterable (list, tuple, or another set) to a set.

## 3. How do you make a link open in a new browser tab?
Use the `target="_blank"` attribute in the anchor tag.

```html
<a href="https://google.com" target="_blank">Google</a>
```

## 4. What is the difference between a compiler and an interpreter?
- **Compiler:** Translates source code into machine code or another target form before execution.
- **Interpreter:** Executes code through an interpreter, often processing it incrementally at runtime.

## 5. What is the use of a dictionary in Python?
A dictionary stores data in key-value pairs. It is used to organize and retrieve values using unique keys.

```python
student = {"name": "Rahul", "age": 22}
```

## 6. When should we use `justify-content` and `align-items`?
Both are Flexbox properties.

- `justify-content` aligns items along the main axis.
- `align-items` aligns items along the cross axis.

## 7. How can we select a `div` inside a class in CSS?
Use a descendant selector (space).

```css
.container div {
    color: red;
}
```

This selects all `div` elements inside `.container`, including nested ones.

## 8. What are five common input types in HTML?

1. `text` – Accepts plain text.
2. `password` – Accepts passwords and hides the entered characters.
3. `email` – Accepts email addresses and provides basic email validation.
4. `number` – Accepts numeric values.
5. `radio` – Allows the user to select one option from a group.

## 9. What is the use of padding in CSS?
Padding creates space between an element's content and its border. It helps improve spacing and readability inside an element.

## 10. What are the four components of the CSS box model?
1. **Content:** Actual text or image.
2. **Padding:** Space around the content.
3. **Border:** Surrounds the padding and content.
4. **Margin:** Space outside the border.

## 11. What is the difference between `absolute` and `relative` positioning in CSS?
- **Relative:** Positions an element relative to its original position and preserves its space.
- **Absolute:** Removes an element from normal document flow and positions it relative to its nearest positioned ancestor.

## 12. What is the difference between `display: none` and `visibility: hidden`?
- `display: none` completely removes the element from the layout.
- `visibility: hidden` hides the element but preserves its space in the layout.

## 13. What is the difference between `span` and `div` in HTML?
- `<div>` is a block-level element used to group larger sections of content.
- `<span>` is an inline element used to style or group small portions of text.

## 14. What is the use of the `<head>` tag in HTML?
The `<head>` tag contains metadata and information about the webpage, such as the title, character encoding, viewport settings, CSS links, and scripts. Its content is generally not displayed on the webpage.

## 15. What is the difference between `RANK()` and `DENSE_RANK()` in SQL?
Both are window functions used to assign rankings to rows.

- `RANK()` assigns the same rank to tied values but skips the next rank.
- `DENSE_RANK()` assigns the same rank to tied values without skipping the next rank.

**Example:**

| Marks | RANK() | DENSE_RANK() |
|---:|---:|---:|
| 95 | 1 | 1 |
| 90 | 2 | 2 |
| 90 | 2 | 2 |
| 85 | 4 | 3 |
