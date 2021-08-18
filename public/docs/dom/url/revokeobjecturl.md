URL.revokeObjectURL()
=====================

The `URL.revokeObjectURL()` static method releases an existing object URL which was previously created by calling [`URL.createObjectURL()`](createobjecturl). Call this method when you've finished using an object URL to let the browser know not to keep the reference to the file any longer.

**Note:** This feature is available in [Web Workers](../web_workers_api).

**Note:** This method is not available from service workers, due to issues with the [`Blob`](../blob) interface's life cycle and the potential for leaks.

Syntax
------

    URL.revokeObjectURL(objectURL)

### Parameters

`objectURL `  
A [`DOMString`](../domstring) representing a object URL that was previously created by calling [`createObjectURL()`](createobjecturl).

Examples
--------

See [Using object URLs to display images](../file/using_files_from_web_applications#example_using_object_urls_to_display_images).

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/FileAPI/#dfn-revokeObjectURL">File API<br />
<span class="small">The definition of 'revokeObjectURL()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`revokeObjectURL`

19

12

19

`revokeObjectURL()` is no longer available within the context of a `ServiceWorker`.

10

15

6

≤37

25

19

`revokeObjectURL()` is no longer available within the context of a `ServiceWorker`.

14

6

1.5

See also
--------

-   [Using files from web applications](../file/using_files_from_web_applications)
-   [Using object URLs to display images](../file/using_files_from_web_applications#example_using_object_urls_to_display_images)
-   [`URL.createObjectURL()`](createobjecturl)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/URL/revokeObjectURL" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/URL/revokeObjectURL</a>
