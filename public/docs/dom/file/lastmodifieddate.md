File.lastModifiedDate
=====================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `File.lastModifiedDate` read-only property returns the last modified date of the file. Files without a known last modified date returns the current date .

Syntax
------

    var time = instanceOfFile.lastModifiedDate

### Value

A `Date` object indicating the date and time at which the file was last modified.

Example
-------

    // fileInput is a HTMLInputElement: <input type="file" multiple id="myfileinput">
    var fileInput = document.getElementById("myfileinput");

    // files is a FileList object (similar to NodeList)
    var files = fileInput.files;

    for (var i = 0; i < files.length; i++) {
      alert(files[i].name + " has a last modified date of " + files[i].lastModifiedDate);
    }

Reduced time precision
----------------------

To offer protection against timing attacks and fingerprinting, the precision of `someFile.lastModifiedDate.getTime()` might get rounded depending on browser settings.

In Firefox, the `privacy.reduceTimerPrecision` preference is enabled by default and defaults to 20us in Firefox 59; in 60 it will be 2ms.

    // reduced time precision (2ms) in Firefox 60
    someFile.lastModifiedDate.getTime();
    // 1519211809934
    // 1519211810362
    // 1519211811670
    // ...

    // reduced time precision with `privacy.resistFingerprinting` enabled
    someFile.lastModifiedDate.getTime();
    // 1519129853500
    // 1519129858900
    // 1519129864400
    // ...

In Firefox, you can also enable `privacy.resistFingerprinting`, the precision will be 100ms or the value of `privacy.resistFingerprinting.reduceTimerPrecision.microseconds`, whichever is larger.

Specifications
--------------

*Though present in early draft of the File API spec, this property has been removed from it and is now non-standard. Use [`File.lastModified`](lastmodified) instead.*

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

`lastModifiedDate`

13

12

15-61

10

16

6.1-10

≤37

Yes

No

No

7-10

Yes

See also
--------

-   [`File`](../file)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/File/lastModifiedDate" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/File/lastModifiedDate</a>
