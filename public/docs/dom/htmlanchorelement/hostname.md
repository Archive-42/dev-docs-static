HTMLAnchorElement.hostname
==========================

The `HTMLAnchorElement.hostname` property is a [`USVString`](../usvstring) containing the domain of the URL.

Syntax
------

    // Getter
    string = anchor.hostname;
    // Setter
    anchor.hostname = string;

Examples
--------

    // An <a id="myAnchor" href="/en-US/docs/HTMLAnchorElement"> element is in the document
    const anchor = document.getElementById("myAnchor");
    anchor.hostname; // returns 'developer.mozilla.org'

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-hyperlink-hostname">HTML Living Standard<br />
<span class="small">The definition of 'HTMLHyperlinkElementUtils.hostname' in that specification.</span></a></td></tr></tbody></table>

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

`hostname`

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

-   The [`HTMLAnchorElement`](../htmlanchorelement) interface it belongs to.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLAnchorElement/hostname" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLAnchorElement/hostname</a>
