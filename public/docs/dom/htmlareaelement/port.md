HTMLAreaElement.port
====================

The `HTMLAreaElement.port` property is a [`USVString`](../usvstring) containing the port number of the URL. If the URL does not contain an explicit port number, it will be set to `''`.

Syntax
------

    // Getter
    string = area.port;
    // Setter
    area.port = string;

Examples
--------

### Getting the port from an area link

    // An <area id="myArea" href="https://developer.mozilla.org:443/en-US/docs/HTMLAreaElement"> element is in the document
    const area = document.getElementByID("myArea");
    area.port; // returns '443'

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-hyperlink-port">HTML Living Standard<br />
<span class="small">The definition of 'HTMLHyperlinkElementUtils.port' in that specification.</span></a></td></tr></tbody></table>

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

`port`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLAreaElement/port" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLAreaElement/port</a>
