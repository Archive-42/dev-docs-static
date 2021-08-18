FileSystemEntry.fullPath
========================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The read-only `fullPath` property of the [`FileSystemEntry`](../filesystementry) interface returns a [`USVString`](../usvstring) specifying the full, absolute path from the file system's root to the file represented by the entry.

This can also be thought of as a path which is relative to the root directory, with a "/" prepended to it to make it absolute.

Syntax
------

    var fullPath = FileSystemEntry.fullPath;

### Value

A [`USVString`](../usvstring) indicating the entry's full path.

Example
-------

This example shows a function which is called with a file system; it then gets a [`FileSystemFileEntry`](../filesystemfileentry) for a file named `data.json` and returns its full path.

    function gotFileSystem(fs) {
      let path = "";

      fs.root.getFile("data.json", { create: true, exclusive: true }, function(entry) {
        path = fullPath;
      }, handleError(error));

      return path;
    }

Obviously, this is somewhat contrived, since we know that the file's full path is `"/data.json"`, having just looked it up ourselves, but the concept holds up for scenarios in which you don't know it.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/entries-api/#dom-filesystementry-fullpath">File and Directory Entries API<br />
<span class="small">The definition of 'fullPath' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial specification.</td></tr></tbody></table>

This API has no official W3C or WHATWG specification.

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

`fullPath`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/FileSystemEntry/fullPath" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/FileSystemEntry/fullPath</a>
