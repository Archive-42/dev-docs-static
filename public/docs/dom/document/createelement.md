# Document.createElement()

In an [HTML](https://developer.mozilla.org/en-US/docs/Web/HTML) document, the `document.createElement()` method creates the HTML element specified by tagName, or an [`HTMLUnknownElement`](../htmlunknownelement) if tagName isn't recognized.

## Syntax

    let element = document.createElement(tagName[, options]);

### Parameters

tagName  
A string that specifies the type of element to be created. The [`nodeName`](../node/nodename) of the created element is initialized with the value of tagName. Don't use qualified names (like "html:a") with this method. When called on an HTML document, `createElement()` converts tagName to lower case before creating the element. In Firefox, Opera, and Chrome, `createElement(null)` works like `createElement("null")`.

options <span class="badge inline optional">Optional</span>  
An optional `ElementCreationOptions` object, containing a single property named `is`, whose value is the tag name of a custom element previously defined via `customElements.define()`. See [Web component example](#web_component_example) for more details.

### Return value

The new [`Element`](../element).

## Examples

### Basic example

This creates a new `<div>` and inserts it before the element with the ID "`div1`".

#### HTML

    <!DOCTYPE html>
    <html>
    <head>
      <title>||Working with elements||</title>
    </head>
    <body>
      <div id="div1">The text above has been created dynamically.</div>
    </body>
    </html>

#### JavaScript

    document.body.onload = addElement;

    function addElement () {
      // create a new div element
      const newDiv = document.createElement("div");

      // and give it some content
      const newContent = document.createTextNode("Hi there and greetings!");

      // add the text node to the newly created div
      newDiv.appendChild(newContent);

      // add the newly created element and its content into the DOM
      const currentDiv = document.getElementById("div1");
      document.body.insertBefore(newDiv, currentDiv);
    }

### Web component example

The following example snippet is taken from our expanding-list-web-component example (see it live also). In this case, our custom element extends the [`HTMLUListElement`](../htmlulistelement), which represents the [`<ul>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/ul) element.

    // Create a class for the element
    class ExpandingList extends HTMLUListElement {
      constructor() {
        // Always call super first in constructor
        super();

        // constructor definition left out for brevity
        ...
      }
    }

    // Define the new element
    customElements.define('expanding-list', ExpandingList, { extends: "ul" });

If we wanted to create an instance of this element programmatically, we'd use a call along the following lines:

    let expandingList = document.createElement('ul', { is : 'expanding-list' })

The new element will be given an `is` attribute whose value is the custom element's tag name.

**Note**: For backwards compatibility with previous versions of the [Custom Elements specification](https://www.w3.org/TR/custom-elements/), some browsers will allow you to pass a string here instead of an object, where the string's value is the custom element's tag name.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-document-createelement">DOM<br />
<span class="small">The definition of 'Document.createElement' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

## Browser compatibility

Desktop

Mobile

Chrome

Edge

Firefox

Internet Explorer

Opera

Safari

WebView Android

Chrome Android

Firefox for Android

Opera Android

Safari on IOS

Samsung Internet

`createElement`

1

12

1

Doesn't conform to the DOM spec for XUL and XHTML documents: `localName` and `namespaceURI` are not set to null on the created element.

5

6

1

1

18

4

10.1

1

1.0

`options`

56

For backwards compatibility, the `options` argument can be an object or a string with the custom element tag name, although the string version is deprecated.

79

For backwards compatibility, the `options` argument can be an object or a string with the custom element tag name, although the string version is deprecated.

50

Firefox accepts a string instead of an object here, but only from version 51 onwards. In version 50, options must be an object.

No

43

For backwards compatibility, the `options` argument can be an object or a string with the custom element tag name, although the string version is deprecated.

No

56

For backwards compatibility, the `options` argument can be an object or a string with the custom element tag name, although the string version is deprecated.

56

For backwards compatibility, the `options` argument can be an object or a string with the custom element tag name, although the string version is deprecated.

50

Firefox accepts a string instead of an object here, but only from version 51 onwards. In version 50, options must be an object.

43

For backwards compatibility, the `options` argument can be an object or a string with the custom element tag name, although the string version is deprecated.

No

6.0

For backwards compatibility, the `options` argument can be an object or a string with the custom element tag name, although the string version is deprecated.

## See also

- [`Node.removeChild()`](../node/removechild)
- [`Node.replaceChild()`](../node/replacechild)
- [`Node.appendChild()`](../node/appendchild)
- [`Node.insertBefore()`](../node/insertbefore)
- [`Node.hasChildNodes()`](../node/haschildnodes)
- [`document.createElementNS()`](createelementns) — to explicitly specify the namespace URI for the element.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/createElement" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document/createElement</a>
