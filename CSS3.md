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

## Internal CSS
An internal style sheet may be used if one single HTML page has a unique style.

The internal style is defined inside the <style> element, inside the head section.

## CSS background - Shorthand property
To shorten the code, it is also possible to specify all the background properties in one single property. This is called a shorthand property.

**Example**
  
Use the shorthand property to set the background properties in one declaration:
  
```
body {
  background: #ffffff url("img_tree.png") no-repeat right top;
}
```
  
When using the shorthand property the order of the property values is:

1. background-color
1. background-image
1. background-position
1. background-size
1. background-repeat
1. background-origin
1. background-clip
1. background-attachment
  
It does not matter if one of the property values is missing, as long as the other ones are in this order.

## CSS Box Model
All HTML elements can be considered as boxes.

In CSS, the term "box model" is used when talking about design and layout.

The CSS box model is essentially a box that wraps around every HTML element. It consists of: margins, borders, padding, and the actual content. The image below illustrates the box model:
  
![image](https://user-images.githubusercontent.com/13497579/132917111-4da1e693-b0da-41fd-8941-c8afb0580d8a.png)

Explanation of the different parts:

- **Content** - The content of the box, where text and images appear
- **Padding** - Clears an area around the content. The padding is transparent
- **Border** - A border that goes around the padding and content
- **Margin** - Clears an area outside the border. The margin is transparent
  
The box model allows us to add a border around elements, and to define space between elements.

## CSS Links
Links can be styled with any CSS property. In addition, links can be styled differently depending on what state they are in.

The four links states are:

- `a:link` - a normal, unvisited link
- `a:visited` - a link the user has visited
- `a:hover` - a link when the user mouses over it
- `a:active` - a link the moment it is clicked
  
MUST be defined in that order.

## CSS Layout - The display property
The display property specifies if/how an element is displayed.

Every HTML element has a default display value depending on what type of element it is. The default display value for most elements is `block` or `inline`.

### Block-level Elements
A block-level element always starts on a new line and takes up the full width available (stretches out to the left and right as far as it can).

The `<div>` element is a block-level element.

### Inline Elements
An inline element does not start on a new line and only takes up as much width as necessary.

This is an inline `<span>` element inside a paragraph.

### Hide an Element - display:none or visibility:hidden?
Hiding an element can be done by setting the `display` property to `none`. The element will be hidden, and the page will be displayed as if the element is not there. Example:
```
h1.hidden {
  display: none;
}
```
  
`visibility:hidden;` also hides an element. However, the element will still take up the same space as before. The element will be hidden, but still affect the layout. Example:

```
h1.hidden {
  visibility: hidden;
}
```
  
## Quick tips
### Center element within its container
You can set the `margin` property to `auto` to horizontally center the element within its container. The element will then take up the specified width, and the remaining space will be split equally between the left and right margins. **Example:**
  
```
div {
  width: 300px;
  margin: auto;
  border: 1px solid red;
}
``` 
  
### \<a> links  
You can set the `text-decoration` property to `none` to remove the underline of the `a` links. **Example:**
  
```
a {
  text-decoration: none;
}
```
  
### Fonts  
If you do not want to use any of the standard fonts in HTML, you can use **Google Fonts**.
  
```
<head>
<link rel="stylesheet" href="https://fonts.googleapis.com/css?family=Sofia">
<style>
body {
  font-family: "Sofia", sans-serif;
}
</style>
</head>
```
  
### Icons
- **Font Awesome**

The simplest way to add an icon to your HTML page, is with an icon library, such as Font Awesome. To use the Font Awesome icons, go to [fontawesome.com](http://www.fontawesome.com), sign in, and get a code to add in the `<head>` section of your HTML page:
```
<script src="https://kit.fontawesome.com/yourcode.js" crossorigin="anonymous"></script>
```

- **Bootstrap glyphicons**
  
To use the Bootstrap glyphicons, add the following line inside the `<head>` section of your HTML page:
```
<link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/css/bootstrap.min.css">
```
  
- **Google Icons**
  
To use the Google icons, add the following line inside the `<head>` section of your HTML page:
```
<link rel="stylesheet" href="https://fonts.googleapis.com/icon?family=Material+Icons">
```

### Striped Tables
  
For zebra-striped tables, use the `nth-child()` selector and add a background-color to all even (or odd) table rows. Example:
```
tr:nth-child(even) {background-color: #f2f2f2;}
```
