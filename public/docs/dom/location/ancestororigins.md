# Location: ancestorOrigins

The `ancestorOrigins` read-only property of the [`Location`](../location) interface is a static [`DOMStringList`](../domstringlist) containing, in reverse order, the origins of all ancestor browsing contexts of the document associated with the given [`Location`](../location) object.

You can use `location.ancestorOrigins` in the script for a document to determine, for example, whenever the document is being framed by a site which you don’t expect it to be framed by. You can also use it to vary the behavior of the document based on what site or list of sites is framing it.

## Syntax

    const ancestors = location.ancestorOrigins;

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-location-ancestororigins">HTML Living Standard<br />
<span class="small">The definition of 'ancestorOrigins ' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`ancestorOrigins`

20

79

No

No

15

6

4.4

25

No

14

6

1.5

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Location/ancestorOrigins" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Location/ancestorOrigins</a>
