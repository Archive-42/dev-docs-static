FileSystemFileHandle
====================

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `FileSystemFileHandle` interface of the [`File System Access API`](file_system_access_api) represents a handle to a file system entry. The interface is accessed thought the [`window.showOpenFilePicker()`](window/showopenfilepicker) method.

Note that read and write operations depend on file-access permissions that do not persist after a page refresh if no other tabs for that origin remain open. The [`queryPermission`](filesystemhandle/querypermission) method of the [`FileSystemHandle`](filesystemhandle) interface can be used to verify permission state before accessing a file.

Properties
----------

*Inherits properties from its parent, [`FileSystemHandle`](filesystemhandle).*

Methods
-------

*Inherits methods from its parent, [`FileSystemHandle`](filesystemhandle).*

[`getFile()`](filesystemfilehandle/getfile)  
Returns a [`file object`](file) representing the state on disk of the entry represented by the handle.

[`createWritable()`](filesystemfilehandle/createwritable)  
Creates a [`FileSystemWritableFileStream`](filesystemwritablefilestream) that can be used to write to a file.

Examples
--------

### Reading a File

The following asynchronous function presents a file picker and once a file is chosen, uses the `getFile()` method to retrieve the contents.

    async function getTheFile() {
      // open file picker
      [fileHandle] = await window.showOpenFilePicker(pickerOpts);

      // get file contents
      const fileData = await fileHandle.getFile();
    }

### Writing a File

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

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/file-system-access/#api-filesystemfilehandle">File System Access API<br />
<span class="small">The definition of 'FileSystemFileHandle' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`FileSystemFileHandle`

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

-   [File System Access API](file_system_access_api)
-   [The File System Access API: simplifying access to local files](https://web.dev/file-system-access/)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/FileSystemFileHandle" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/FileSystemFileHandle</a>
