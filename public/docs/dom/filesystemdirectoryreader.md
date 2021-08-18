FileSystemDirectoryReader
=========================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

The `FileSystemDirectoryReader` interface of the [File and Directory Entries API](file_and_directory_entries_api) lets you access the [`FileEntry`](filesystemfileentry)-based objects (generally [`FileSystemFileEntry`](filesystemfileentry) or [`FileSystemDirectoryEntry`](filesystemdirectoryentry)) representing each entry in a directory.

Because this is a non-standard API, whose specification is not currently on a standards track, it's important to keep in mind that not all browsers implement it, and those that do may implement only small portions of it. Check the [Browser compatibility](#browser_compatibility) section for details.

Methods
-------

 [`readEntries()`](filesystemdirectoryreader/readentries) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
Returns an array containing some number of the directory's entries. Each item in the array is an object based on [`FileSystemEntry`](filesystementry)—typically either [`FileSystemFileEntry`](filesystemfileentry) or [`FileSystemDirectoryEntry`](filesystemdirectoryentry).

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/entries-api/">File and Directory Entries API</a></td><td><span class="spec-draft">Draft</span></td><td>Draft of proposed API</td></tr></tbody></table>

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

`FileSystemDirectoryReader`

8

≤18

50

No

Yes

11.1

≤37

18

50

No

11.3

1.0

`readEntries`

8

?

Yes

No

?

11.1

≤37

18

Yes

No

11.3

1.0

See also
--------

-   [File and Directory Entries API](file_and_directory_entries_api)
-   [Introduction to the File System API](file_and_directory_entries_api/introduction)
-   [`FileSystemDirectoryEntry`](filesystemdirectoryentry)
-   [`FileSystem`](filesystem)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/FileSystemDirectoryReader" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/FileSystemDirectoryReader</a>
