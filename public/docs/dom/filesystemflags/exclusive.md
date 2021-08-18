FileSystemFlags.exclusive
=========================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `exclusive` property on the [`FileSystemFlags`](../filesystemflags) dictionary is used in tandem with the create property to determine whether or not it's acceptable to require that the file not already exist when the reference to it is created by calling [`FileSystemDirectoryEntry.getFile()`](../filesystemdirectoryentry/getfile) or [`FileSystemDirectoryEntry.getDirectory()`](../filesystemdirectoryentry/getdirectory).

Syntax
------

    fileSystemFlags.exclusive = booleanValue

### Values

The table below describes the result of each possible combination of these flags depending on whether or not the target file or directory path already exists.

Option values

File/directory condition

Result

[`create`](create)

[`exclusive`](exclusive)

`false`

n/a<sup>\[1\]</sup>

Path exists and matches the desired type (depending on whether the function called is `getFile()` or `getDirectory()`

The `successCallback` is called with a [`FileSystemFileEntry`](../filesystemfileentry) if `getFile()` was called or a [`FileSystemDirectoryEntry`](../filesystemdirectoryentry) if `getDirectory()` was called.

`false`

n/a<sup>\[1\]</sup>

Path exists but doesn't match the desired type

The `errorCallback` is called with an appropriate error code (if the callback was provided).

`true`

`false`

Path exists

The existing file or directory is removed and replaced with a new one, then the `successCallback` is called with a [`FileSystemFileEntry`](../filesystemfileentry) or a [`FileSystemDirectoryEntry`](../filesystemdirectoryentry), as appropriate.

`true`

`false`

Path doesn't exist

The file or directory is created, then a [`FileSystemFileEntry`](../filesystemfileentry) or a [`FileSystemDirectoryEntry`](../filesystemdirectoryentry) is passed to the `successCallback`, as appropriate.

`true`

`true`

Path exists

The `errorCallback` is called with an appropriate error, such as `FileError.PATH_EXISTS_ERR`.

`true`

`true`

Path doesn't exist

The file or directory is created, then a [`FileSystemFileEntry`](../filesystemfileentry) or a [`FileSystemDirectoryEntry`](../filesystemdirectoryentry) is passed to the `successCallback`, as appropriate.

\[1\] When `create` is `false`, the value of `exclusive` is irrelevant and ignored.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/entries-api/#dom-filesystemflags-exclusive">File and Directory Entries API<br />
<span class="small">The definition of 'FileSystemFlags' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial specification.</td></tr></tbody></table>

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

`exclusive`

13

≤79

50

For security reasons, Firefox does not support creating files. This option has no effect.

No

No

No

≤37

Yes

50

For security reasons, Firefox does not support creating files. This option has no effect.

No

No

Yes

See also
--------

-   [File and Directory Entries API](../file_and_directory_entries_api)
-   [Introduction to the File System API](../file_and_directory_entries_api/introduction)
-   [`FileSystemFlags`](../filesystemflags)
-   [`FileSystemDirectoryEntry.getFile()`](../filesystemdirectoryentry/getfile) and [`FileSystemDirectoryEntry.getDirectory()`](../filesystemdirectoryentry/getdirectory)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/FileSystemFlags/exclusive" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/FileSystemFlags/exclusive</a>
