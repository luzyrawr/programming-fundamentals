# CSS3
## CSS Selectors
CSS selectors are used to "find" (or select) the HTML elements you want to style.

We can divide CSS selectors into five categories:
1. Simple selectors (select elements based on name, id, class)
1. Combinator selectors (select elements based on a specific relationship between them)
1. Pseudo-class selectors (select elements based on a certain state)
1. Pseudo-elements selectors (select and style a part of an element)
1. Attribute selectors (select elements based on an attribute or attribute value)

## Simple selectors
| Selector | Example | Example description |
| --- | --- | --- |
| #id | #firstname | Selects the element with id="firstname" |
| .class | .intro | Selects all elements with class="intro" |
| element.class | p.intro| Selects only `<p>` elements with class="intro" |
| * | * | Selects all elements |
| element | p | Selects all `<p>` elements |
| element,element,.. | div, p | Selects all `<div>` elements and all `<p>` elements |

## Add external style sheet
Each HTML page must include a reference to the external style sheet file inside the <link> element, inside the head section.
```
<link rel="stylesheet" href="mystyle.css">
```
