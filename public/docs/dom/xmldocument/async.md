XMLDocument.async
=================

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

`document.async` can be set to indicate whether a [`XMLDocument.load()`](load) call should be an asynchronous or synchronous request. `true` is the default value, indicating that documents should be loaded asynchronously.

(It has been possible to load documents synchronously since 1.4 alpha.)

Example
-------

    function loadXMLData(e) {
      alert(new XMLSerializer().serializeToString(e.target)); // Gives querydata.xml contents as string
    }

    var xmlDoc = document.implementation.createDocument("", "test", null);

    xmlDoc.async = false;
    xmlDoc.onload = loadXMLData;
    xmlDoc.load('querydata.xml');

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

`async`

No

No

1-68

See [bug 1328138](https://bugzil.la/1328138) for removal.

No

No

No

No

No

4-68

See [bug 1328138](https://bugzil.la/1328138) for removal.

No

No

No

See also
--------

-   [XML in Mozilla](https://developer.mozilla.org/en-US/docs/XML_in_Mozilla)
-   [`XMLDocument.load()`](load)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XMLDocument/async" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XMLDocument/async</a>
