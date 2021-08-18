FileSystemEntry.name
====================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The read-only `name` property of the [`FileSystemEntry`](../filesystementry) interface returns a [`USVString`](../usvstring) specifying the entry's name; this is the entry within its parent directory (the last component of the path as indicated by the [`fullPath`](fullpath) property).

Syntax
------

    var name = FileSystemEntry.name;

### Value

A [`USVString`](../usvstring) indicating the entry's name.

Example
-------

This example shows a function called `isFileWithExtension()` which returns true if the specified [`FileSystemEntry`](../filesystementry) is both a file and the file's name ends with a given extension.

    function isFileWithExtension(entry, extension) {
      return (entry.isFile && entry.name.endsWith("." + extension));
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/entries-api/#dom-filesystementry-name">File and Directory Entries API<br />
<span class="small">The definition of 'name' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial specification.</td></tr></tbody></table>

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

`name`

8

79

50

No

No

11.1

≤37

18

50

No

11.3

1.0

See also
--------

-   [File and Directory Entries API](../file_and_directory_entries_api)
-   [Introduction to the File System API](../file_and_directory_entries_api/introduction)
-   [`FileSystemEntry`](../filesystementry)
-   [`FileSystemEntry.fullPath`](fullpath)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/FileSystemEntry/name" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/FileSystemEntry/name</a>
