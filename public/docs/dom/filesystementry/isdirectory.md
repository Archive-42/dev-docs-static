FileSystemEntry.isDirectory
===========================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The read-only `isDirectory` property of the [`FileSystemEntry`](../filesystementry) interface is `true` if the entry represents a directory (meaning it's a [`FileSystemDirectoryEntry`](../filesystemdirectoryentry)) and `false` if it's not.

You can also use [`isFile`](isfile) to determine if the entry is a file.

You should not assume that any entry which isn't a directory is a file or vice-versa. There are other types of file descriptors on many operating systems. Be sure to use both `isDirectory` and `isFile` as needed to ensure that the entry is something you know how to work with.

Syntax
------

    var isDirectory = FileSystemEntry.isDirectory;

### Value

A Boolean indicating whether or not the [`FileSystemEntry`](../filesystementry) is a directory.

Example
-------

This example shows how this property might be used to determine whether to process the entry as a directory or file. If the entry is neither, an error handler is called with an appropriate message.

    if (entry.isDirectory) {
      processSubdirectory(entry);
    } else if (entry.isFile) {
      processFile(entry);
    } else {
      displayErrorMessage("Unsupported file system entry specified.");
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/entries-api/#dom-filesystementry-isdirectory">File and Directory Entries API<br />
<span class="small">The definition of 'isDirectory' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial specification.</td></tr></tbody></table>

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

`isDirectory`

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
-   [`FileSystemEntry.isFile`](isfile)
-   [`FileSystemDirectoryEntry`](../filesystemdirectoryentry)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/FileSystemEntry/isDirectory" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/FileSystemEntry/isDirectory</a>
