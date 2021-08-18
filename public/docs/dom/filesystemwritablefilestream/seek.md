# FileSystemWritableFileStream.seek()

**Draft**

This page is not complete.

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `seek()` method of the [`FileSystemWritableFileStream`](../filesystemwritablefilestream) interface updates the current file cursor offset to the position (in bytes) specified when calling the method.

## Syntax

    FileSystemWritableStream.seek(position).then(...);

### Parameters

`position`  
An unsigned long describing the byte position from the top (beginning) of the file.

### Return value

[`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) which returns undefined.

### Exceptions

NotAllowedError  
If the [`PermissionStatus.state`](../permissionstatus/state) is not 'granted'.

TypeError  
If `position` is not defined or of type unsigned long.

## Examples

Todo

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/file-system-access/#api-filesystemwritablefilestream-seek">File System Access API<br />
<span class="small">The definition of 'seek' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`seek`

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

## See also

- [File System Access API](../file_system_access_api)
- [The File System Access API: simplifying access to local files](https://web.dev/file-system-access/)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/FileSystemWritableFileStream/seek" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/FileSystemWritableFileStream/seek</a>
