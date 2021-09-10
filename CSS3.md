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
