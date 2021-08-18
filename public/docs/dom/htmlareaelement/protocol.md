HTMLAreaElement.protocol
========================

The `HTMLAreaElement.protocol` property is a [`USVString`](../usvstring) representing the protocol scheme of the URL, including the final `':'`.

Syntax
------

    // Getter
    string = area.protocol;
    // Setter
    area.protocol = string;

Examples
--------

### Getting the protocol of an area link

    // An <area id="myArea" href="https://developer.mozilla.org/en-US/HTMLAreaElement"> element is in the document
    const area = document.getElementById("myArea");
    area.protocol; // returns 'https:'

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-hyperlink-protocol">HTML Living Standard<br />
<span class="small">The definition of 'HTMLHyperlinkElementUtils.protocol' in that specification.</span></a></td></tr></tbody></table>

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

`protocol`

1

12

1

5

15

1

1

18

4

14

1

1.0

See also
--------

-   The [`HTMLAreaElement`](../htmlareaelement) interface it belongs to.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLAreaElement/protocol" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLAreaElement/protocol</a>
