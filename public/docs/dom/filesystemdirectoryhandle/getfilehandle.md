# FileSystemDirectoryHandle.getFileHandle()

**Draft**

This page is not complete.

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `getFileHandle()` method of the [`FileSystemDirectoryHandle`](../filesystemdirectoryhandle) interface returns a [`FileSystemFileHandle`](../filesystemfilehandle) for a file with the specified name, within the directory the method is called.

## Syntax

    var FileSystemFileHandle = FileSystemDirectoryHandle.getFileHandle(name);

### Parameters

_name_  
A [`USVString`](../usvstring) representing the [`FileSystemHandle.name`](../filesystemhandle/name) of the file you wish to retrieve.

_options_ <span class="badge inline optional">Optional</span>

- `create`: A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean). Default `false`. When set to `true` if the file is not found, one with the specified name will be created and returned.

### Return value

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) which resolves with a [`FileSystemFileHandle`](../filesystemfilehandle).

### Exceptions

`NotAllowedError`  
If [`PermissionStatus`](../permissionstatus) is not 'granted'.

`TypeError`  
If the name specified is not a valid string or contains characters that would interfere with the native file system

`TypeMismatchError`  
If the named entry is a directory and not a file.

`NotFoundError`  
if file doesn't exist and the `create` option is set to `false`.

## Examples

The following example returns a file handle with the specified name, if the file does not exist it is created.

    const fileName = 'fileToGetName';

    // assuming we have a directory handle: 'currentDirHandle'
    const fileHandle = currentDirHandle.getFileHandle(fileName, {create: true});

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/file-system-access/#api-filesystemdirectoryhandle-getfilehandle">File System Access API<br />
<span class="small">The definition of 'getFileHandle' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`getFileHandle`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/FileSystemDirectoryHandle/getFileHandle" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/FileSystemDirectoryHandle/getFileHandle</a>
