HTMLLinkElement.referrerPolicy
==============================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `HTMLLinkElement``.referrerPolicy` property reflect the HTML [`referrerpolicy`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/link#attr-referrerpolicy) attribute of the [`<link>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/link) element defining which referrer is sent when fetching the resource.

See the HTTP [`Referrer-Policy`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Referrer-Policy) header for details.

Syntax
------

    DOMString HTMLLinkElement.referrerPolicy

Example
-------

    var links = document.getElementsByTagName("link");
    links[0].referrerPolicy; // "no-referrer"

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webappsec-referrer-policy/#referrer-policy-delivery-referrer-attribute">Referrer Policy<br />
<span class="small">The definition of 'referrerPolicy attribute' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td></td></tr></tbody></table>

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

`referrerPolicy`

58

79

50

No

45

14.1

58

58

50

43

14.5

7.0

See also
--------

-   HTTP header [`Referrer-Policy`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Referrer-Policy)
-   [`HTMLAnchorElement.referrerPolicy`](../htmlanchorelement/referrerpolicy)
-   [`HTMLAreaElement.referrerPolicy`](../htmlareaelement/referrerpolicy)
-   [`HTMLIFrameElement.referrerPolicy`](../htmliframeelement/referrerpolicy)
-   [`HTMLImageElement.referrerPolicy`](../htmlimageelement/referrerpolicy)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLLinkElement/referrerPolicy" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLLinkElement/referrerPolicy</a>
