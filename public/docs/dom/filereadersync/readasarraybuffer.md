# FileReaderSync.readAsArrayBuffer()

The `readAsArrayBuffer()` method of the [`FileReaderSync`](../filereadersync) interface allows to read [`File`](../file) or [`Blob`](../blob) objects in a synchronous way into an [`ArrayBuffer`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer). This interface is [only available](../web_workers_api/functions_and_classes_available_to_workers) in [workers](../worker) as it enables synchronous I/O that could potentially block.

## Syntax

    ArrayBuffer readAsArrayBuffer(
      in Blob blob
    );

### Parameters

`blob`  
The DOM [`File`](../file) or [`Blob`](../blob) to read into the [`File`](../file) or [`ArrayBuffer`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer).

### Return value

An [`ArrayBuffer`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer) representing the file's data.

## Exceptions

The following exceptions can be raised by this method:

`NotFoundError`  
is raised when the resource represented by the DOM [`File`](../file) or [`Blob`](../blob) cannot be found, e.g. because it has been erased.

`SecurityError`  
is raised when one of the following problematic situation is detected:

- the resource has been modified by a third party;
- too many read are performed simultaneously;
- the file pointed by the resource is unsafe for a use from the Web (like it is a system file).

`NotReadableError`  
is raised when the resource cannot be read due to a permission problem, like a concurrent lock.

`EncodingError`  
is raised when the resource is a data URL and exceed the limit length defined by each browser.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/FileAPI/#dfn-readAsArrayBufferSync">File API<br />
<span class="small">The definition of 'readAsArrayBufferSync' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`readAsArrayBuffer`

7

12

8

10

≤12.1

6-6.1

≤37

18

8

≤12.1

6-7

1.0

## See also

- [File API](https://developer.mozilla.org/en-US/docs/API/File_API)
- [`File`](../file)
- [`FileReaderSync`](../filereadersync)
- [`FileReader`](../filereader)
- [`BlobBuilder`](../blobbuilder), [`Blob`](../blob)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/FileReaderSync/readAsArrayBuffer" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/FileReaderSync/readAsArrayBuffer</a>
