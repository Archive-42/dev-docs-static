# FileReaderSync

The `FileReaderSync` interface allows to read [`File`](file) or [`Blob`](blob) objects synchronously.

**Note:** This feature is available in [Web Workers](web_workers_api).

This interface is **only available** in [workers](worker) as it enables synchronous I/O that could potentially block.

## Properties

This interface does not have any properties.

## Methods

[`FileReaderSync.readAsArrayBuffer()`](filereadersync/readasarraybuffer)  
This method converts a specified [`Blob`](blob) or a [`File`](file) into an [`ArrayBuffer`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer) representing the input data as a binary string.

[`FileReaderSync.readAsBinaryString()`](filereadersync/readasbinarystring) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
This method converts a specified [`Blob`](blob) or a [`File`](file) into a [`DOMString`](domstring) representing the input data as a binary string. This method is deprecated, consider using `readAsArrayBuffer()` instead.

[`FileReaderSync.readAsText()`](filereadersync/readastext)  
This method converts a specified [`Blob`](blob) or a [`File`](file) into a [`DOMString`](domstring) representing the input data as a text string. The optional `encoding` parameter indicates the encoding to be used (e.g., iso-8859-1 or UTF-8). If not present, the method will apply a detection algorithm for it.

[`FileReaderSync.readAsDataURL()`](filereadersync/readasdataurl)  
This method converts a specified [`Blob`](blob) or a [`File`](file) into a [`DOMString`](domstring) representing the input data as a data URL.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/FileAPI/#FileReaderSync">File API<br />
<span class="small">The definition of 'FileReaderSync' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`FileReaderSync`

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

`FileReaderSync`

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

`readAsDataURL`

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

`readAsText`

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

`worker_support`

Yes

From Chrome 59, not supported in service workers.

12

Not supported in service workers.

8

From Firefox 61, not supported in service workers.

Yes

Yes

From Opera 46, not supported in service workers.

Yes-6.1

Not supported in service workers.

Yes

From version 59, not supported in service workers.

Yes

From Chrome 59, not supported in service workers.

8

From Firefox 61, not supported in service workers.

Yes

From Opera 43, not supported in service workers.

Yes-7

Not supported in service workers.

Yes

From version 7.0, not supported in service workers.

## See also

- [`FileReader`](filereader)
- [`BlobBuilder`](blobbuilder), [`Blob`](blob)
- [`File`](file)
- [`FileReader`](filereader)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/FileReaderSync" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/FileReaderSync</a>
