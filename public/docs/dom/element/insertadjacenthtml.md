Element.insertAdjacentHTML()
============================

The `insertAdjacentHTML()` method of the [`Element`](../element) interface parses the specified text as HTML or XML and inserts the resulting nodes into the DOM tree at a specified position. It does not reparse the element it is being used on, and thus it does not corrupt the existing elements inside that element. This avoids the extra step of serialization, making it much faster than direct [`innerHTML`](innerhtml) manipulation.

Syntax
------

    element.insertAdjacentHTML(position, text);

### Parameters

`position`  
A [`DOMString`](../domstring) representing the position relative to the `element`; must be one of the following strings:

-   `'beforebegin'`: Before the `element` itself.
-   `'afterbegin'`: Just inside the `element`, before its first child.
-   `'beforeend'`: Just inside the `element`, after its last child.
-   `'afterend'`: After the `element` itself.

`text`  
The string to be parsed as HTML or XML and inserted into the tree.

### Visualization of position names

    <!-- beforebegin -->
    <p>
      <!-- afterbegin -->
      foo
      <!-- beforeend -->
    </p>
    <!-- afterend -->

**Note:** The `beforebegin` and `afterend` positions work only if the node is in the DOM tree and has a parent element.

Example
-------

    // <div id="one">one</div>
    var d1 = document.getElementById('one');
    d1.insertAdjacentHTML('afterend', '<div id="two">two</div>');

    // At this point, the new structure is:
    // <div id="one">one</div><div id="two">two</div>

Notes
-----

### Security considerations

When inserting HTML into a page by using `insertAdjacentHTML()`, be careful not to use user input that hasn't been escaped.

It is not recommended you use `insertAdjacentHTML()` when inserting plain text; instead, use the [`Node.textContent`](../node/textcontent) property or the [`Element.insertAdjacentText()`](insertadjacenttext) method. This doesn't interpret the passed content as HTML, but instead inserts it as raw text.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/DOM-Parsing/#dom-element-insertadjacenthtml">DOM Parsing and Serialization<br />
<span class="small">The definition of 'Element.insertAdjacentHTML()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

Browser compatibility
---------------------

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

`insertAdjacentHTML`

1

17

12-17

Only supported for [`HTMLElement`](https://developer.mozilla.org/docs/Web/API/HTMLElement), not all `Element` objects, such as [`SVGElement`](https://developer.mozilla.org/docs/Web/API/SVGElement).

8

4

\["Before Internet Explorer 10, throws an \\"Invalid target element for this operation.\\" error when called on a `<table>`, `<tbody>`, `<thead>`, or `<tr>` element.", "Only supported for [`HTMLElement`](https://developer.mozilla.org/docs/Web/API/HTMLElement), not all `Element` objects, such as [`SVGElement`](https://developer.mozilla.org/docs/Web/API/SVGElement)."\]

8

4

1

18

8

10.1

4

1.0

See also
--------

-   [`Element.insertAdjacentElement()`](insertadjacentelement)
-   [`Element.insertAdjacentText()`](insertadjacenttext)
-   [`XMLSerializer`](../xmlserializer): Construct a DOM representation of XML text
-   [hacks.mozilla.org guest post](https://hacks.mozilla.org/2011/11/insertadjacenthtml-enables-faster-html-snippet-injection/)<span class="external"> by Henri Sivonen including benchmark showing that insertAdjacentHTML can be way faster in some cases.</span>

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/insertAdjacentHTML" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element/insertAdjacentHTML</a>
