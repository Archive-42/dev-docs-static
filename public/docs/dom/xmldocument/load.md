XMLDocument.load()
==================

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

`document.load()` is a part of an old version of the W3C [DOM Level 3 Load & Save module](https://www.w3.org/TR/2003/WD-DOM-Level-3-LS-20030619/load-save.html#LS-DocumentLS). Can be used with [`document.async`](async) to indicate whether the request is synchronous or asynchronous (the default). As of at least Gecko 1.9, this no longer supports cross-site loading of documents (Use [`XMLHttpRequest`](../xmlhttprequest) or [`fetch()`](../windoworworkerglobalscope/fetch) instead).

Examples
--------

    var xmlDoc = document.implementation.createDocument("", "test", null);

    function documentLoaded (e) {
      alert(new XMLSerializer().serializeToString(e.target)); // Gives querydata.xml contents as string
    }

    xmlDoc.addEventListener("load", documentLoaded, false);
    xmlDoc.load('querydata.xml');

[See also the load sample](https://dxr.mozilla.org/mozilla-central/source/content/xml/tests/load/) in the XML tests directory. (To test this functionality, create the files on your local disk or on a webserver rather than loading the load.html file from the LXR-generated page, which will serve the text.xml file as HTML.)

Specifications
--------------

-   [Old W3C Working Draft of the DOM Level 3 Load & Save module](https://www.w3.org/TR/2003/WD-DOM-Level-3-LS-20030619/load-save.html#LS-DocumentLS)

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

`load`

No

No

3-68

See [bug 332175](https://bugzil.la/332175) for removal.

1-3

Before version 3, Firefox supported cross-origin loads, even in cases where this would violate CORS.

No

No

No

No

No

4-68

See [bug 332175](https://bugzil.la/332175) for removal.

No

No

No

See also
--------

-   [`XMLDocument.async`](async)
-   [XML in Mozilla](https://developer.mozilla.org/en-US/docs/XML_in_Mozilla)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XMLDocument/load" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XMLDocument/load</a>
