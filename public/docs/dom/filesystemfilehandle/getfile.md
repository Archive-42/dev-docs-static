FileSystemFileHandle.getFile()
==============================

**Draft**

This page is not complete.

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `getFile()` method of the [`FileSystemFileHandle`](../filesystemfilehandle) interface returns a [`file   object`](../file) representing the state on disk of the entry represented by the handle.

If the file on disk changes or is removed after this method is called, the returned [`file object`](../file) will likely be no longer readable.

Syntax
------

    var File = FileSystemFileHandle.getFile();

### Parameters

None.

### Return value

A [`File object`](../file).

### Exceptions

NotAllowedError  
Thrown if the [`PermissionStatus.state`](../permissionstatus/state) is not `granted` in read mode.

Examples
--------

The following asynchronous function presents a file picker and once a file is chosen, uses the `getFile()` method to retrieve the contents.

    async function getTheFile() {
      // open file picker
      [fileHandle] = await window.showOpenFilePicker(pickerOpts);

      // get file contents
      const fileData = await fileHandle.getFile();
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/file-system-access/#api-filesystemfilehandle-getfile">File System Access API<br />
<span class="small">The definition of 'getFile' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`getFile`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/FileSystemFileHandle/getFile" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/FileSystemFileHandle/getFile</a>
