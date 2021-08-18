MimeTypeArray
=============

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `MimeTypeArray` interface returns an array of [`MimeType`](mimetype) instances, each of which contains information about a supported browser plugins. This object is returned by [`NavigatorPlugins.mimeTypes`](navigatorplugins/mimetypes).

Properties
----------

<span class="page-not-created">`MimeTypeArray.length`</span>  
The number of items in the array.

Methods
-------

<span class="page-not-created">`MimeTypeArray.item()`</span>  
Returns the `MimeType` object with the specified index.

<span class="page-not-created">`MimeTypeArray.namedItem()`</span>  
Returns the `MimeType` object with the specified name.

Example
-------

The following example tests whether a plugin is available for the application/pdf mime type and if so, which plugin that is.

    var mimeTypes = navigator.mimeTypes;
    var flashPlugin = mimeTypes['video/x-flv'];
    if (typeof flashPlugin === "undefined") {
      var vid = document.createElement('video');
      // Use vid.canPlayType() to test for a supported mime type.
    } else {
      // Notify the user that flash is being deprecated and they
      //   should upgrade their browser.
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#mimetypearray">HTML Living Standard<br />
<span class="small">The definition of 'MimeTypeArray' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`MimeTypeArray`

1

12

1

?

≤12.1

1

1

18

4

≤12.1

1

1.0

`item`

1

Prior to version 59, method parameters were optional

12

1

?

≤12.1

4

1

Prior to version 59, method parameters were optional

18

Prior to version 59, method parameters were optional

4

≤12.1

3.2

1.0

Prior to Samsung Internet 7.0, method parameters were optional

`length`

1

12

1

?

≤12.1

Yes

1

18

4

≤12.1

Yes

1.0

`namedItem`

1

Prior to version 59, method parameters were optional

12

1

?

≤12.1

4

1

Prior to version 59, method parameters were optional

18

Prior to version 59, method parameters were optional

4

≤12.1

3.2

1.0

Prior to Samsung Internet 7.0, method parameters were optional

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MimeTypeArray" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MimeTypeArray</a>
