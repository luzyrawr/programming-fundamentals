# HTML
## Semantic Elements
> Semantic elements = elements with a meaning.

A semantic element clearly describes its meaning to both the browser and the developer.

Examples of non-semantic elements: `<div>` and `<span>` - Tells nothing about its content.

Examples of semantic elements: `<form>`, `<table>`, and `<article>` - Clearly defines its content.

A semantic Web allows data to be shared and reused across applications, enterprises, and communities.

## Layout Elements

HTML has several semantic elements that define the different parts of a web page:

![image](https://user-images.githubusercontent.com/13497579/132418193-e2e563a7-f62f-4e25-bf25-b375f66b787e.png)

- `<article>` - Defines an independent, self-contained content
- `<aside>` - Defines content aside from the content (like a sidebar)
- `<details>` - Defines additional details that the user can open and close on demand
- `<figcaption>` - Defines a caption for a `<figure>` element. The `<figcaption>` element can be placed as the first or as the last child of a `<figure>` element.
- `<figure>` - Specifies self-contained content, like illustrations, diagrams, photos, code listings, etc
- `<footer>` - Defines a footer for a document or a section
- `<header>` - Defines a header for a document or a section
- `<main>` - Specifies the main content of a document
- `<mark>` - Defines marked/highlighted text
- `<nav>` - Defines a set of navigation links
- `<section>` - Defines a section in a document
- `<summary>` - Defines a heading for the \<details> element
- `<time>` - Defines a date/time



## Layout Techniques

There are four different techniques to create multicolumn layouts. Each technique has its pros and cons:

- **CSS framework.** If you want to create your layout fast, you can use a CSS framework, like Bootstrap.
- **CSS float property.** It is common to do entire web layouts using the CSS float property. Float is easy to learn - you just need to remember how the float and clear properties work. Disadvantages: Floating elements are tied to the document flow, which may harm the flexibility.
- **CSS flexbox.** Use of flexbox ensures that elements behave predictably when the page layout must accommodate different screen sizes and different display devices.
- **CSS grid.** The CSS Grid Layout Module offers a grid-based layout system, with rows and columns, making it easier to design web pages without having to use floats and positioning.

## URL Encoding

- URLs can only be sent over the Internet using the ASCII character-set. If a URL contains characters outside the ASCII set, the URL has to be converted.
- URL encoding converts non-ASCII characters into a format that can be transmitted over the Internet.
- URL encoding replaces non-ASCII characters with a "%" followed by hexadecimal digits.
- URLs cannot contain spaces. URL encoding normally replaces a space with a plus (+) sign, or %20.

## Forms

An HTML form is used to collect user input. The user input is most often sent to a server for processing. 

**\<form>**

The HTML `<form>` element is used to create an HTML form for user input. The HTML `<form>` element is a container for different types of input elements, such as: text fields, checkboxes, radio buttons, submit buttons, etc.

**\<label>**

The `<label>` tag defines a label for many form elements. The **for attribute** of the `<label>` tag should be equal to the **id attribute** of the <input> element to bind them together. When you click the `<label>` tag it focuses the element binded to it.

**\<input type="submit"> or Submit Button**

The `<input type="submit">` defines a button for submitting the form data to a form-handler. The form-handler is typically a file on the server with a script for processing input data. The form-handler is specified in the **action attribute** of the `<form>`.

**\<input>**
Notice that each input field must have a **name attribute** to be submitted. If the **name attribute** is omitted, the value of the input field will not be sent at all.

### \<form> Atrributes

- **accept-charset**	Specifies the character encodings used for form submission
- **action**	Specifies where to send the form-data when a form is submitted
- **autocomplete**	Specifies whether a form should have autocomplete on or off
- **enctype**	Specifies how the form-data should be encoded when submitting it to the server (only for method="post")
- **method**	Specifies the HTTP method to use when sending form-data
- **name**	Specifies the name of the form
- **novalidate**	Specifies that the form should not be validated when submitted
- **rel**	Specifies the relationship between a linked resource and the current document
- **target**	Specifies where to display the response that is received after submitting the form
