FileSystemSync
==============

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

In the [File System API](file_and_directory_entries_api/introduction), a `FileSystemSync `object represents a file system. It has two properties.

About this document
-------------------

This document was last updated on March 2, 2012 and follows the [W3C Specifications (Working Draft)](https://www.w3.org/TR/file-system-api/) drafted on April 19, 2011.

The specification is abandoned for the moment, failing to get significant traction.

Basic concepts
--------------

The `FileSystemSync` object is your gateway to the entire API and you will use it a lot. So once you have a reference, cache the object in a global variable or class property.

Attributes
----------

<table><thead><tr class="header"><th>Attribute</th><th>Type</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><span id="attr_name"><code>name</code></span></td><td><code>readonly DOMString</code></td><td>Name of the file system. The name must be unique across the list of exposed file systems.</td></tr><tr class="even"><td><span id="attr_root"><code>root</code></span></td><td><code>readonly DirectoryEntry</code></td><td>The root directory of the file system.</td></tr></tbody></table>

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

`FileSystemSync`

13

≤79

No

No

15

6

≤37

18

No

14

6

1.0

`name`

13

≤79

No

No

15

6

≤37

18

No

14

6

1.0

`root`

13

≤79

No

No

15

6

≤37

18

No

14

6

1.0

See also
--------

Specification:[File API: Directories and System Specification](https://dev.w3.org/2009/dap/file-system/pub/FileSystem/)WD

Reference: [File System API](file_and_directory_entries_api/introduction)

Introduction: [Basic Concepts About the File System API](file_and_directory_entries_api/introduction)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/FileSystemSync" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/FileSystemSync</a>
