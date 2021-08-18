# FileSystemWritableFileStream.write()

**Draft**

This page is not complete.

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `write()` method of the [`FileSystemWritableFileStream`](../filesystemwritablefilestream) interface writes content into the file the method is called on, at the current file cursor offset.

No changes are written to the actual file on disk until the stream has been closed. Changes are typically written to a temporary file instead. This method can also be used to seek to a byte point within the stream and truncate to modify the total bytes the file contains.

## Syntax

    FileSystemWritableFileStream.write(data).then(...);

### Parameters

`data`  
Can be either the file data to write, in the form of a [`BufferSource`](../buffersource), [`Blob`](../blob) or [`USVString`](../usvstring). Or an object containing the following properties:

- `type`: One of `'write'`, `'seek'` or `'truncate'`. This is required if the object is passed into the `write()` method.
- `data`: The file data to write. Can be a [`BufferSource`](../buffersource), [`Blob`](../blob) or [`USVString`](../usvstring). This is required if the `type` is set to `'write'`.
- `position`: The byte position the current file cursor should move to if type `'seek'` is used. Can also be set with `'write'` in which case the write will start at the position.
- `size`: An unsigned long value representing the amount of bytes the stream should contain. This is required if the `type` is set to `'truncate'`

### Return value

[`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) which returns undefined

### Exceptions

NotAllowedError  
If [`PermissionStatus`](../permissionstatus) is not granted.

TypeError  
If data is undefined, or if `position` or `size` aren't valid.

InvalidStateError  
If the `position` is set and larger than the bytes available.

## Examples

This asynchronous function opens the 'Save File' picker, which returns a [`FileSystemFileHandle`](../filesystemfilehandle) once a file is selected. From which a writable stream is then created using the [`FileSystemFileHandle.createWritable()`](../filesystemfilehandle/createwritable) method.

A user defined [`Blob`](../blob) is then written to the stream which is subsequently closed.

    async function saveFile() {

      // create a new handle
      const newHandle = await window.showSaveFilePicker();

      // create a FileSystemWritableFileStream to write to
      const writableStream = await newHandle.createWritable();

      // write our file
      await writableStream.write(imgBlob);

      // close the file and write the contents to disk.
      await writableStream.close();
    }

The following show different examples of options that can be passed into the `write()` method.

    // just pass in the data (no options)
    writableStream.write(data)

    // writes the data to the stream from the determined position
    writableStream.write({ type: "write", position: position, data: data })

    // updates the current file cursor offset to the position specified
    writableStream.write({ type: "seek", position: position })

    // resizes the file to be size bytes long
    writableStream.write({ type: "truncate", size: size })

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/file-system-access/#api-filesystemwritablefilestream-write">File System Access API<br />
<span class="small">The definition of 'write' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`write`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/FileSystemWritableFileStream/write" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/FileSystemWritableFileStream/write</a>
