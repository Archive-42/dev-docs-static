FileSystemDirectoryHandle.resolve()
===================================

**Draft**

This page is not complete.

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `resolve()` method of the [`FileSystemDirectoryHandle`](../filesystemdirectoryhandle) interface returns an [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) of directory names from the parent handle to the specified child entry, with the name of the child entry as the last array item.

Syntax
------

    var pathArr = FileSystemDirectoryHandle.resolve(possibleDescendant);

### Parameters

possibleDescendant  
The [`FileSystemHandle.name`](../filesystemhandle/name) of the [`FileSystemHandle`](../filesystemhandle) from which to return the relative path.

### Return value

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) which resolves with an [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) of <span class="page-not-created">`strings`</span>.

### Exceptions

No exceptions are thrown.

Examples
--------

The following asynchronous function uses `resolve()` to find the path to a chosen file, relative to a specified directory handle.

    async function returnPathDirectories(directoryHandle) {

      // Get a file handle by showing a file picker:
      const handle = await self.showOpenFilePicker();
      if (!handle) {
        // User cancelled, or otherwise failed to open a file.
        return;
      }

      // Check if handle exists inside our directory handle
      const relativePaths = await directoryHandle.resolve(handle);

      if (relativePath === null) {
        // Not inside directory handle
      } else {
        // relativePath is an array of names, giving the relative path

        for (const name of relativePaths) {
          // log each entry
          console.log(name);
        }
      }
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/file-system-access/#dom-filesystemdirectoryhandle-resolve">File System Access API<br />
<span class="small">The definition of 'resolve' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`resolve`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/FileSystemDirectoryHandle/resolve" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/FileSystemDirectoryHandle/resolve</a>
