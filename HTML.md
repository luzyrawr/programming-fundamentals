# HTML
## HTML Semantic Elements
> Semantic elements = elements with a meaning.

A semantic element clearly describes its meaning to both the browser and the developer.

Examples of non-semantic elements: `<div>` and `<span>` - Tells nothing about its content.

Examples of semantic elements: `<form>`, `<table>`, and `<article>` - Clearly defines its content.

## HTML Layout Elements

HTML has several semantic elements that define the different parts of a web page:

![image](https://user-images.githubusercontent.com/13497579/132418193-e2e563a7-f62f-4e25-bf25-b375f66b787e.png)

- `<article>` - Defines an independent, self-contained content
- `<aside>` - Defines content aside from the content (like a sidebar)
- `<details>` - Defines additional details that the user can open and close on demand
- `<figcaption>`
- `<figure>`
- `<footer>` - Defines a footer for a document or a section
- `<header>` - Defines a header for a document or a section
- `<main>`
- `<mark>`
- `<nav>` - Defines a set of navigation links
- `<section>` - Defines a section in a document
- `<summary>` - Defines a heading for the \<details> element
- `<time>`



## HTML Layout Techniques

There are four different techniques to create multicolumn layouts. Each technique has its pros and cons:

- **CSS framework.** If you want to create your layout fast, you can use a CSS framework, like Bootstrap.
- **CSS float property.** It is common to do entire web layouts using the CSS float property. Float is easy to learn - you just need to remember how the float and clear properties work. Disadvantages: Floating elements are tied to the document flow, which may harm the flexibility.
- **CSS flexbox.** Use of flexbox ensures that elements behave predictably when the page layout must accommodate different screen sizes and different display devices.
- **CSS grid.** The CSS Grid Layout Module offers a grid-based layout system, with rows and columns, making it easier to design web pages without having to use floats and positioning.
