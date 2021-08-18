# Document.getElementById()

The [`Document`](../document) method `getElementById()` returns an [`Element`](../element) object representing the element whose [`id`](../element/id) property matches the specified string. Since element IDs are required to be unique if specified, they're a useful way to get access to a specific element quickly.

If you need to get access to an element which doesn't have an ID, you can use [`querySelector()`](queryselector) to find the element using any [selector](https://developer.mozilla.org/en-US/docs/Glossary/CSS_Selector).

## Syntax

    var element = document.getElementById(id);

### Parameters

`id`  
The ID of the element to locate. The ID is case-sensitive string which is unique within the document; only one element may have any given ID.

### Return value

An [`Element`](../element) object describing the DOM element object matching the specified ID, or `null` if no matching element was found in the document.

## Example

### HTML

    <html>
    <head>
      <title>getElementById example</title>
    </head>
    <body>
      <p id="para">Some text here</p>
      <button onclick="changeColor('blue');">blue</button>
      <button onclick="changeColor('red');">red</button>
    </body>
    </html>

### JavaScript

    function changeColor(newColor) {
      var elem = document.getElementById('para');
      elem.style.color = newColor;
    }

### Result

## Usage notes

The capitalization of `"Id"` in the name of this method _must_ be correct for the code to function; `getElementByID()` is _not_ valid and will not work, however natural it may seem.

Unlike some other element-lookup methods such as [`Document.querySelector()`](queryselector) and [`Document.querySelectorAll()`](queryselectorall), `getElementById()` is only available as a method of the global `document` object, and _not_ available as a method on all element objects in the DOM. Because ID values must be unique throughout the entire document, there is no need for "local" versions of the function.

## Example

    <!doctype html>
    <html>
    <head>
        <meta charset="UTF-8">
        <title>Document</title>
    </head>
    <body>
        <div id="parent-id">
            <p>hello word1</p>
            <p id="test1">hello word2</p>
            <p>hello word3</p>
            <p>hello word4</p>
        </div>
        <script>
            var parentDOM = document.getElementById('parent-id');
            var test1 = parentDOM.getElementById('test1');
            //throw error
            //Uncaught TypeError: parentDOM.getElementById is not a function
        </script>
    </body>
    </html>

If there is no element with the given `id`, this function returns `null`. Note that the `id` parameter is case-sensitive, so `document.getElementById("Main")` will return `null` instead of the element `<div id="main">` because "M" and "m" are different for the purposes of this method.

**Elements not in the document** are not searched by `getElementById()`. When creating an element and assigning it an ID, you have to insert the element into the document tree with [`Node.insertBefore()`](../node/insertbefore) or a similar method before you can access it with `getElementById()`:

    var element = document.createElement('div');
    element.id = 'testqq';
    var el = document.getElementById('testqq'); // el will be null!

**Non-HTML documents**. The DOM implementation must have information that says which attributes are of type ID. Attributes with the name "id" are not of type ID unless so defined in the document's DTD. The `id` attribute is defined to be of ID type in the common cases of [XHTML](https://developer.mozilla.org/en-US/docs/Glossary/XHTML), [XUL](https://developer.mozilla.org/en-US/docs/XUL), and other. Implementations that do not know whether attributes are of type ID or not are expected to return `null`.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/REC-DOM-Level-1/level-one-html.html#method-getElementById">Document Object Model (DOM) Level 1 Specification<br />
<span class="small">The definition of 'getElementById' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition for the interface</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-2-Core/core.html#ID-getElBId">Document Object Model (DOM) Level 2 Core Specification<br />
<span class="small">The definition of 'getElementById' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Supersede DOM 1</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/DOM-Level-3-Core/core.html#ID-getElBId">Document Object Model (DOM) Level 3 Core Specification<br />
<span class="small">The definition of 'getElementById' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Supersede DOM 2</td></tr><tr class="even"><td><a href="https://dom.spec.whatwg.org/#dom-nonelementparentnode-getelementbyid">DOM<br />
<span class="small">The definition of 'getElementById' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Intend to supersede DOM 3</td></tr></tbody></table>

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

`getElementById`

1

12

1

5.5

7

1

1

18

4

10.1

1

1.0

## See also

- [`Document`](../document) reference for other methods and properties you can use to get references to elements in the document.
- [`Document.querySelector()`](queryselector) for selectors via queries like `'div.myclass'`
- [xml:id](https://developer.mozilla.org/en-US/docs/xml/xml:id) - has a utility method for allowing `getElementById()` to obtain 'xml:id' in XML documents (such as returned by Ajax calls)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/getElementById" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document/getElementById</a>
