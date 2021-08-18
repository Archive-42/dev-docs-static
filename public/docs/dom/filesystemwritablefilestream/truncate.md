FileSystemWritableFileStream.truncate()
=======================================

**Draft**

This page is not complete.

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `truncate()` method of the [`FileSystemWritableFileStream`](../filesystemwritablefilestream) interface resizes the file associated with the stream to be the specified size in bytes.

If the size specified is larger than the current file size this pads the file with `null` bytes, otherwise it truncates the file.

The file cursor is also updated when `truncate()` is called. If the offset is smaller than the size, it remains unchanged. If the offset is larger than size, the offset is set to that size. This ensures that subsequent writes do not error.

No changes are written to the actual file on disk until the stream has been closed. Changes are typically written to a temporary file instead.

Syntax
------

    FileSystemWritableFileStream.truncate().then(...);

### Parameters

size  
An `unsigned long` of the amount of bytes to resize the stream to.

### Return value

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) which returns undefined.

### Exceptions

NotAllowedError  
If the <span class="page-not-created">`PermissionState`</span> is not 'granted'.

TypeError  
If the size is undefined or not an unsigned long.

Examples
--------

    // todo

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/file-system-access/#api-filesystemwritablefilestream-truncate">File System Access API<br />
<span class="small">The definition of 'truncate' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`truncate`

86

86

No

No

No

No

No

No

No

No

No

No

See also
--------

-   [File System Access API](../file_system_access_api)
-   [The File System Access API: simplifying access to local files](https://web.dev/file-system-access/)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/FileSystemWritableFileStream/truncate" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/FileSystemWritableFileStream/truncate</a>
