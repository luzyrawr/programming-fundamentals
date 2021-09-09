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

### \<form>

The HTML `<form>` element is used to create an HTML form for user input. The HTML `<form>` element is a container for different types of input elements, such as: text fields, checkboxes, radio buttons, submit buttons, etc.

### \<label>

The `<label>` tag defines a label for many form elements. The **for attribute** of the `<label>` tag should be equal to the **id attribute** of the <input> element to bind them together. When you click the `<label>` tag it focuses the element binded to it.

### \<input type="submit"> or Submit Button

The `<input type="submit">` defines a button for submitting the form data to a form-handler. The form-handler is typically a file on the server with a script for processing input data. The form-handler is specified in the **action attribute** of the `<form>`.

### \<input>
Notice that each input field must have a **name attribute** to be submitted. If the **name attribute** is omitted, the value of the input field will not be sent at all.

## \<form> Atrributes

- **accept-charset**	Specifies the character encodings used for form submission
- **action**	Specifies where to send the form-data when a form is submitted
- **autocomplete**	Specifies whether a form should have autocomplete on or off
- **enctype**	Specifies how the form-data should be encoded when submitting it to the server (only for method="post")
- **method**	Specifies the HTTP method to use when sending form-data
- **name**	Specifies the name of the form
- **novalidate**	Specifies that the form should not be validated when submitted
- **rel**	Specifies the relationship between a linked resource and the current document
- **target**	Specifies where to display the response that is received after submitting the form

## Form Elements
- `<form>`	Defines an HTML form for user input
- `<input>`	Defines an input control
- `<textarea>`	Defines a multiline input control (text area)
- `<label>`	Defines a label for an <input> element
- `<fieldset>`	Groups related elements in a form
- `<legend>`	Defines a caption for a <fieldset> element
- `<select>`	Defines a drop-down list
- `<optgroup>`	Defines a group of related options in a drop-down list
- `<option>`	Defines an option in a drop-down list
- `<button>`	Defines a clickable button
- `<datalist>`	Specifies a list of pre-defined options for input controls
- `<output>`	Defines the result of a calculation

## Input Types
Here are the different input types you can use in HTML:
- `<input type="button">`
- `<input type="checkbox">`
- `<input type="color">`
- `<input type="date">`
- `<input type="datetime-local">`
- `<input type="email">`
- `<input type="file">`
- `<input type="hidden">`
- `<input type="image">`
- `<input type="month">`
- `<input type="number">`
- `<input type="password">`
- `<input type="radio">`
- `<input type="range">`
- `<input type="reset">`
- `<input type="search">`
- `<input type="submit">`
- `<input type="tel">`
- `<input type="text">`
- `<input type="time">`
- `<input type="url">`
- `<input type="week">`
  
### The readonly Attribute
The input `readonly` attribute specifies that an input field is read-only.

A read-only input field cannot be modified (however, a user can tab to it, highlight it, and copy the text from it).

The value of a read-only input field will be sent when submitting the form!
  
### The disabled Attribute
The input `disabled` attribute specifies that an input field should be disabled.

A disabled input field is unusable and un-clickable.

The value of a disabled input field will not be sent when submitting the form!
  
## Web Storage API

With web storage, web applications can store data locally within the user's browser.

Before HTML5, application data had to be stored in cookies, included in every server request. Web storage is more secure, and large amounts of data can be stored locally, without affecting website performance.

Unlike cookies, the storage limit is far larger (at least 5MB) and information is never transferred to the server.

Web storage is per origin (per domain and protocol). All pages, from one origin, can store and access the same data.
  
### Web Storage Objects

HTML web storage provides two objects for storing data on the client:

- `window.localStorage` - stores data with no expiration date
- `window.sessionStorage` - stores data for one session (data is lost when the browser tab is closed)
  
Before using web storage, check browser support for localStorage and sessionStorage:
```
  if (typeof(Storage) !== "undefined") {
    // Code for localStorage/sessionStorage.
  } else {
    // Sorry! No Web Storage support..
  }
```

## Web Workers API
When executing scripts in an HTML page, the page becomes unresponsive until the script is finished.

A web worker is a JavaScript that runs in the background, independently of other scripts, without affecting the performance of the page. You can continue to do whatever you want: clicking, selecting things, etc., while the web worker runs in the background.

### Check Web Worker Support
Before creating a web worker, check whether the user's browser supports it:

```
  if (typeof(Worker) !== "undefined") {
    // Yes! Web worker support!
    // Some code.....
  } else {
    // Sorry! No Web Worker support..
  }
```
  
### Create a Web Worker File
Now, let's create our web worker in an external JavaScript.

Here, we create a script that counts. The script is stored in the "demo_workers.js" file:

```
  var i = 0;

  function timedCount() {
    i = i + 1;
    postMessage(i);
    setTimeout("timedCount()",500);
  }
  
  timedCount();
```

The important part of the code above is the `postMessage()` method - which is used to post a message back to the HTML page.

### Create a Web Worker Object
Now that we have the web worker file, we need to call it from an HTML page.

The following lines checks if the worker already exists, if not - it creates a new web worker object and runs the code in "demo_workers.js":

```
if (typeof(w) == "undefined") {
  w = new Worker("demo_workers.js");
}
```
  
Then we can send and receive messages from the web worker.

Add an "onmessage" event listener to the web worker.
  
```
w.onmessage = function(event){
  document.getElementById("result").innerHTML = event.data;
};
```
  
When the web worker posts a message, the code within the event listener is executed. The data from the web worker is stored in event.data.

### Terminate a Web Worker
When a web worker object is created, it will continue to listen for messages (even after the external script is finished) until it is terminated.

To terminate a web worker, and free browser/computer resources, use the terminate() method:
```
w.terminate();
```
  
### Reuse the Web Worker
If you set the worker variable to undefined, after it has been terminated, you can reuse the code:
  
```
w = undefined;
```
