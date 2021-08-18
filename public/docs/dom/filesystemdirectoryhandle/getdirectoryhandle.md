FileSystemDirectoryHandle.getDirectoryHandle()
==============================================

**Draft**

This page is not complete.

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `getDirectoryHandle()` method of the [`FileSystemDirectoryHandle`](../filesystemdirectoryhandle) interface returns a [`FileSystemDirectoryHandle`](../filesystemdirectoryhandle) for a subdirectory with the specified name within the directory handle on which the method is called.

Syntax
------

    var FileSystemDirectoryHandle = FileSystemDirectoryHandle.getDirectoryHandle();

### Parameters

*name*  
A [`USVString`](../usvstring) representing the [`FileSystemHandle.name`](../filesystemhandle/name) of the subdirectory you wish to retrieve.

 *options* <span class="badge inline optional">Optional</span>   
An optional object containing options for the retrieved subdirectory. Options are as follows:

-   `create`: A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean). Default `false`. When set to `true` if the directory is not found, one with the specified name will be created and returned.

### Return value

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) which resolves with a [`FileSystemDirectoryHandle`](../filesystemdirectoryhandle).

### Exceptions

`NotAllowedError`  
If [`PermissionStatus`](../permissionstatus) is not 'granted'.

`TypeMismatchError`  
If the returned entry is a file and not a directory.

`NotFoundError`  
if directory doesn't exist and the `create` option is set to `false`.

Examples
--------

The following example returns a directory handle with the specified name, if the directory does not exist it is created.

    const dirName = 'directoryToGetName';

    // assuming we have a directory handle: 'currentDirHandle'
    const subDir = currentDirHandle.getDirectoryHandle(dirName, {create: true});

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/file-system-access/#dom-filesystemdirectoryhandle-getdirectoryhandle">File System Access API<br />
<span class="small">The definition of 'getDirectoryHandle' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`getDirectoryHandle`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/FileSystemDirectoryHandle/getDirectoryHandle" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/FileSystemDirectoryHandle/getDirectoryHandle</a>
