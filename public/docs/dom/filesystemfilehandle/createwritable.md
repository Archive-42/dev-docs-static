FileSystemFileHandle.createWritable()
=====================================

**Draft**

This page is not complete.

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `createWritable()` method of the [`FileSystemFileHandle`](../filesystemfilehandle) interface creates a [`FileSystemWritableFileStream`](../filesystemwritablefilestream) that can be used to write to a file.

Any changes made through the stream won’t be reflected in the file represented by the file handle until the stream has been closed. This is typically implemented by writing data to a temporary file, and only replacing the file represented by file handle with the temporary file when the writable filestream is closed.

Syntax
------

    var FileSystemWritableFileStream = FileSystemFileHandle.createWritable();

### Parameters

FileSystemCreateWritableOptions  
An object representing options to pass into the method. Options are:

-   `keepExistingData`: If `false` or not specified, the temporary file starts out empty, otherwise the existing file is first copied to this temporary file.

### Return value

A Promise which resolves with a [`FileSystemWritableFileStream`](../filesystemwritablefilestream).

### Exceptions

NotAllowedError  
Thrown if the [`PermissionStatus.state`](../permissionstatus/state) for the handle is not `'granted'` in `readwrite` mode.

Examples
--------

The following asynchronous function writes the given contents to the file handle, and thus to disk.

    async function writeFile(fileHandle, contents) {
      // Create a FileSystemWritableFileStream to write to.
      const writable = await fileHandle.createWritable();

      // Write the contents of the file to the stream.
      await writable.write(contents);

      // Close the file and write the contents to disk.
      await writable.close();
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/file-system-access/#dom-filesystemfilehandle-createwritable">File System Access API<br />
<span class="small">The definition of 'createWritable' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`createWritable`

86

86

No

No

72

No

No

86

No

No

No

14.0

See also
--------

-   [File System Access API](../file_system_access_api)
-   [The File System Access API: simplifying access to local files](https://web.dev/file-system-access/)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/FileSystemFileHandle/createWritable" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/FileSystemFileHandle/createWritable</a>
