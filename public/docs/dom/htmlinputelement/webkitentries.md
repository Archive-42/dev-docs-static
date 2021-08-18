HTMLInputElement.webkitEntries
==============================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

The read-only `webkitEntries` property of the [`HTMLInputElement`](../htmlinputelement) interface contains an array of file system entries (as objects based on [`FileSystemEntry`](../filesystementry)) representing files and/or directories selected by the user using an [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input) element of type `file`, but only if that selection was made using drag-and-drop: selecting a file in the dialog will leave the property empty (bug 1326031).

The array can only contain directories if the [`webkitdirectory`](webkitdirectory) property is `true`. This means the `<input>` element was configured to let the user choose directories.

This property is called `webkitEntries` in the specification due to its origins as a Google Chrome-specific API. It's likely to be renamed someday.

Syntax
------

    var entries = HTMLInputElement.webkitEntries;

### Value

An array of objects based on [`FileSystemEntry`](../filesystementry), each representing one file which is selected in the [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input) element. More specifically, files are represented by [`FileSystemFileEntry`](../filesystemfileentry) objects, and, if they're allowed, directories are represented by [`FileSystemDirectoryEntry`](../filesystemdirectoryentry) objects.

Example
-------

This example shows how to create a file selection `<input>` element and process the selected files.

### HTML

    <input id="files" type="file" multiple>

### JavaScript

    document.getElementById("files").addEventListener("change", function(event) {
      event.target.webkitEntries.forEach(function(entry) {
        /* do stuff with the entry */
      });
    });

Each time a `change` event occurs, this code iterates over the selected files, obtaining their [`FileSystemEntry`](../filesystementry)-based objects and acting on them.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/entries-api/#dom-htmlinputelement-webkitentries">File and Directory Entries API<br />
<span class="small">The definition of 'webkitEntries' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial specification.</td></tr></tbody></table>

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

`webkitEntries`

22

79

50

No

15

11.1

≤37

25

No

14

11.3

1.5

See also
--------

-   [File and Directory Entries API](../file_and_directory_entries_api)
-   [Introduction to the File System API](../file_and_directory_entries_api/introduction)
-   [`HTMLInputElement`](../htmlinputelement)
-   [`FileSystemEntry`](../filesystementry)
-   [`FileSystem`](../filesystem)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement/webkitEntries" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement/webkitEntries</a>
