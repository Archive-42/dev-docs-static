# FileReader.readAsArrayBuffer()

The [`FileReader`](../filereader) interface's `readAsArrayBuffer()` method is used to start reading the contents of a specified [`Blob`](../blob) or [`File`](../file). When the read operation is finished, the [`readyState`](readystate) becomes `DONE`, and the [`loadend`](loadend_event) is triggered. At that time, the [`result`](result) attribute contains an [`ArrayBuffer`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer) representing the file's data.

**Newer API available**  
The [`Blob.arrayBuffer()`](../blob/arraybuffer) method is a newer promise-based API to read a file as an array buffer.

## Syntax

    instanceOfFileReader.readAsArrayBuffer(blob);

### Parameters

`blob`  
The [`Blob`](../blob) or [`File`](../file) from which to read.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/FileAPI/#readAsArrayBuffer">File API<br />
<span class="small">The definition of 'FileReader.readAsArrayBuffer' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

3.6

10

12

6

≤37

18

32

12

6

1.0

## See also

- [`FileReader`](../filereader)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/FileReader/readAsArrayBuffer" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/FileReader/readAsArrayBuffer</a>
