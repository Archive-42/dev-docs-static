Element.outerHTML
=================

The `outerHTML` attribute of the [`Element`](../element) DOM interface gets the serialized HTML fragment describing the element including its descendants. It can also be set to replace the element with nodes parsed from the given string.

To only obtain the HTML representation of the contents of an element, or to replace the contents of an element, use the [`innerHTML`](innerhtml) property instead.

Syntax
------

    var content = element.outerHTML;

    element.outerHTML = htmlString;

### Value

Reading the value of `outerHTML` returns a [`DOMString`](../domstring) containing an HTML serialization of the `element` and its descendants. Setting the value of `outerHTML` replaces the element and all of its descendants with a new DOM tree constructed by parsing the specified `htmlString`.

### Exceptions

`SyntaxError`  
An attempt was made to set `outerHTML` using an HTML string which is not valid.

`NoModificationAllowedError`  
An attempt was made to set `outerHTML` on an element which is a direct child of a [`Document`](../document), such as [`Document.documentElement`](../document/documentelement).

Examples
--------

Getting the value of an element's `outerHTML` property:

### HTML

    <div id="d">
      <p>Content</p>
      <p>Further Elaborated</p>
    </div>

### Javascript

    var d = document.getElementById("d");
    console.log(d.outerHTML);

    // The string '<div id="d"><p>Content</p><p>Further Elaborated</p></div>'
    // is written to the console window

Replacing a node by setting the `outerHTML` property:

### HTML

    <div id="container">
      <div id="d">This is a div.</div>
    </div>

### Javascript

    var container = document.getElementById("container");
    var d = document.getElementById("d");

    console.log(container.firstElementChild.nodeName); // logs "DIV"

    d.outerHTML = "<p>This paragraph replaced the original div.</p>";

    console.log(container.firstElementChild.nodeName); // logs "P"

    // The #d div is no longer part of the document tree,
    // the new paragraph replaced it.

Notes
-----

If the element has no parent element, setting its `outerHTML` property will not change it or its descendants. Many browsers will also throw an exception. For example:

    var div = document.createElement("div");
    div.outerHTML = "<div class=\"test\">test</div>";
    console.log(div.outerHTML); // output: "<div></div>"

Also, while the element will be replaced in the document, the variable whose `outerHTML` property was set will still hold a reference to the original element:

    var p = document.getElementsByTagName("p")[0];
    console.log(p.nodeName); // shows: "P"
    p.outerHTML = "<div>This div replaced a paragraph.</div>";
    console.log(p.nodeName); // still "P";

The returned value will contain html escaped attributes:

    var anc = document.createElement("a");
    anc.href = "https://developer.mozilla.org?a=b&c=d";
    console.log(anc.outerHTML); // output: "<a href='https://developer.mozilla.org?a=b&amp;c=d'></a>"

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/DOM-Parsing/#dom-element-outerhtml">DOM Parsing and Serialization<br />
<span class="small">The definition of 'Element.outerHTML' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`outerHTML`

33

This API was previously available on the `Node` API.

12

11

4

8

9

4.4

This API was previously available on the `Node` API.

33

This API was previously available on the `Node` API.

14

10.1

9

2.0

This API was previously available on the `Node` API.

See also
--------

-   Serializing DOM trees into XML or HTML: [`XMLSerializer`](../xmlserializer)
-   Parsing XML or HTML into DOM trees: [`DOMParser`](../domparser)
-   [`HTMLElement.outerText`](../htmlelement/outertext)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/outerHTML" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element/outerHTML</a>
