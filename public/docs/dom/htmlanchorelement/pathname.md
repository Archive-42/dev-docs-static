HTMLAnchorElement.pathname
==========================

The `HTMLAnchorElement.pathname` property is a [`USVString`](../usvstring) containing an initial `'/'` followed by the path of the URL not including the query string or fragment (or the empty string if there is no path).

Syntax
------

    // Getter
    string = anchor.pathname;
    // Setter
    anchor.pathname = string;

Examples
--------

    // An <a id="myAnchor" href="/en-US/docs/HTMLAnchorElement"> element is in the document
    const anchor = document.getElementById("myAnchor");
    anchor.pathname; // returns '/en-US/docs/HTMLAnchorElement'

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-hyperlink-pathname">HTML Living Standard<br />
<span class="small">The definition of 'HTMLHyperlinkElementUtils.pathname' in that specification.</span></a></td></tr></tbody></table>

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

`pathname`

1

12

1

Before Firefox 53, the `pathname` and `search` `HTMLHyperlinkElementUtils` properties returned the wrong parts of the URL. For example, for a URL of `http://z.com/x?a=true&b=false`, `pathname` would return `'/x?a=true&b=false'` and `search` would return '', rather than `'/x'` and `'?a=true&b=false'` respectively. This has now been fixed.

5

15

1

1

18

4

Before Firefox 53, the `pathname` and `search` `HTMLHyperlinkElementUtils` properties returned the wrong parts of the URL. For example, for a URL of `http://z.com/x?a=true&b=false`, `pathname` would return `'/x?a=true&b=false'` and `search` would return '', rather than `'/x'` and `'?a=true&b=false'` respectively. This has now been fixed.

14

1

1.0

See also
--------

-   The [`HTMLAnchorElement`](../htmlanchorelement) interface it belongs to.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLAnchorElement/pathname" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLAnchorElement/pathname</a>
