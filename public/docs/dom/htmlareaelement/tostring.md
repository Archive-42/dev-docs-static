HTMLAreaElement.toString()
==========================

The `HTMLAreaElement.toString()` stringifier method returns a [`USVString`](../usvstring) containing the whole URL. It is a read-only version of [`HTMLAreaElement.href`](href).

Syntax
------

    area.toString();

Examples
--------

### Calling toString on an area element

    // An <area id="myArea" href="/en-US/docs/HTMLAreaElement"> element is in the document
    const area = document.getElementById("myArea");
    area.toString(); // returns 'https://developer.mozilla.org/en-US/docs/HTMLAreaElement'

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-hyperlink-href">HTML Living Standard<br />
<span class="small">The definition of 'HTMLHyperlinkElementUtils.href' in that specification.</span></a></td></tr></tbody></table>

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

`toString`

52

≤18

22

No

Yes

Yes

52

52

22

Yes

Yes

6.0

See also
--------

-   The [`HTMLAreaElement`](../htmlareaelement) interface it belongs to.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLAreaElement/toString" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLAreaElement/toString</a>
