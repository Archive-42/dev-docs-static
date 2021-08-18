# FileReaderSync.readAsBinaryString()

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

**Note:** This method is deprecated in favor of [`readAsArrayBuffer()`](readasarraybuffer).

The `readAsBinaryString()` method of the [`FileReaderSync`](../filereadersync) interface allows to read [`File`](../file) or [`Blob`](../blob) objects in a synchronous way into an [`DOMString`](../domstring). This interface is [only available](../web_workers_api/functions_and_classes_available_to_workers) in [workers](../worker) as it enables synchronous I/O that could potentially block.

## Syntax

    readAsBinaryString(File);
    readAsBinaryString(Blob);

### Parameters

`blob`  
The DOM [`File`](../file) or [`Blob`](../blob) to read.

### Return value

An [`DOMString`](../domstring) representing the input data.

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

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/FileAPI/#dfn-readAsBinaryStringSync">File API<br />
<span class="small">The definition of 'readAsBinaryStringSync' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`readAsBinaryString`

7

12

8

11

15

6-6.1

≤37

18

8

14

6-7

1.0

## See also

- [File API](https://developer.mozilla.org/en-US/docs/API/File_API)
- [`File`](../file)
- [`FileReaderSync`](../filereadersync)
- [`FileReader`](../filereader)
- [`BlobBuilder`](../blobbuilder), [`Blob`](../blob)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/FileReaderSync/readAsBinaryString" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/FileReaderSync/readAsBinaryString</a>
