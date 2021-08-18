FileSystemHandle.requestPermission()
====================================

**Draft**

This page is not complete.

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `requestPermission()` method of the [`FileSystemHandle`](../filesystemhandle) interface requests read or readwrite permissions for the file handle.

Syntax
------

    var PermissionState = FileSystemHandle.requestPermission(FileSystemHandlePermissionDescriptor);

### Parameters

FileSystemHandlePermissionDescriptor <span class="badge inline optional">Optional</span>   
An object which specifies the permission mode to query for. Options are as follows:

-   `'mode'`: Can be either `'read'` or `'readwrite'`.

### Return value

[`PermissionStatus.state`](../permissionstatus/state) which is one of `'granted'`, `'denied'` or `'prompt'`.

### Exceptions

`TypeError`  
No parameter is specified or the `mode` is not that of `'read'` or `'readwrite'`

Examples
--------

The following asynchronous function requests permissions if they have not been granted.

    // fileHandle is a FileSystemFileHandle
    // withWrite is a boolean set to true if write

    async function verifyPermission(fileHandle, withWrite) {
      const opts = {};
      if (withWrite) {
        opts.mode = 'readwrite';
      }

      // Check if we already have permission, if so, return true.
      if (await fileHandle.queryPermission(opts) === 'granted') {
        return true;
      }

      // Request permission to the file, if the user grants permission, return true.
      if (await fileHandle.requestPermission(opts) === 'granted') {
        return true;
      }

      // The user did not grant permission, return false.
      return false;
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/file-system-access/#api-filesystemhandle-requestpermission">File System Access API<br />
<span class="small">The definition of 'requestPermission' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`requestPermission`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/FileSystemHandle/requestPermission" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/FileSystemHandle/requestPermission</a>
