# FileSystemDirectoryHandle.removeEntry()

**Draft**

This page is not complete.

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `removeEntry()` method of the [`FileSystemDirectoryHandle`](../filesystemdirectoryhandle) interface attempts to remove an entry if the directory handle contains a file or directory called the name specified.

## Syntax

    FileSystemDirectoryHandle.removeEntry(name).then...

### Parameters

_name_  
A [`USVString`](../usvstring) representing the [`FileSystemHandle.name`](../filesystemhandle/name) of the entry you wish to remove.

_options_ <span class="badge inline optional">Optional</span>  
An optional object containing options, which are as follows:

- `recursive`: A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean). Default `false`. When set to `true` entries will be removed recursively.

### Return value

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) which resolves with `undefined`.

### Exceptions

`TypeError`  
If the name is not a valid string or contains characters not allowed on the file system

`NotAllowedError`  
If [`PermissionStatus`](../permissionstatus) is not 'granted'.

`InvalidModificationError`  
If `recursive` is set to false and the entry to be removed has children.

`NotFoundError`  
If an entry name is not found or matched

## Examples

The following example removes an entry within the directory handle.

    const entryName = 'entryToRemove';

    // assuming we have a directory handle: 'currentDirHandle'
    currentDirHandle.removeEntry(entryName).then( () => {
      // code to run if removing was successful
    } );

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/file-system-access/#api-filesystemdirectoryhandle-removeentry">File System Access API<br />
<span class="small">The definition of 'removeEntry' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`removeEntry`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/FileSystemDirectoryHandle/removeEntry" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/FileSystemDirectoryHandle/removeEntry</a>
