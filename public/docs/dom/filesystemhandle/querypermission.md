# FileSystemHandle.queryPermission()

**Draft**

This page is not complete.

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `queryPermission()` method of the [`FileSystemHandle`](../filesystemhandle) interface queries the current permission state of the current handle.

## Syntax

    var PermissionState = FileSystemHandle.queryPermission(FileSystemHandlePermissionDescriptor);

### Parameters

FileSystemHandlePermissionDescriptor <span class="badge inline optional">Optional</span>  
An object which specifies the permission mode to query for. Options are as follows:

- `'mode'`: Can be either `'read'` or `'readwrite'`.

### Return value

[`PermissionStatus.state`](../permissionstatus/state) which is one of `'granted'`, `'denied'` or `'prompt'`.

If this returns "prompt" the website will have to call requestPermission() before any operations on the handle can be done. If this returns "denied" any operations will reject. Usually handles returned by the local file system handle factories will initially return "granted" for their read permission state. However, other than through the user revoking permission, a handle retrieved from IndexedDB is also likely to return "prompt".

### Exceptions

`TypeError`  
If `mode` is specified with a value other than `'read'` or `'readwrite'`

## Examples

The following asynchronous function returns true if user has granted read or readwrite permissions to the file handle. Permission is requested if not.

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

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/file-system-access/#api-filesystemhandle-querypermission">File System Access API<br />
<span class="small">The definition of 'queryPermission' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

## Browser compatibility

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

`queryPermission`

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

## See also

- [File System Access API](../file_system_access_api)
- [The File System Access API: simplifying access to local files](https://web.dev/file-system-access/)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/FileSystemHandle/queryPermission" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/FileSystemHandle/queryPermission</a>
