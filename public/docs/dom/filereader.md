# FileReader

The `FileReader` object lets web applications asynchronously read the contents of files (or raw data buffers) stored on the user's computer, using [`File`](file) or [`Blob`](blob) objects to specify the file or data to read.

File objects may be obtained from a [`FileList`](filelist) object returned as a result of a user selecting files using the [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input) element, from a drag and drop operation's [`DataTransfer`](datatransfer) object, or from the `mozGetAsFile()` API on an [`HTMLCanvasElement`](htmlcanvaselement).

`FileReader` can only access the contents of files that the user has explicitly selected, either using an HTML `<input type="file">` element or by drag and drop. It cannot be used to read a file by pathname from the user's file system. To read files on the client's file system by pathname, use the [File System Access API](file_system_access_api). To read server-side files, use standard Ajax solutions, with CORS permission if reading cross-domain.

**Note:** This feature is available in [Web Workers](web_workers_api).

## Constructor

[`FileReader()`](filereader/filereader)  
Returns a newly constructed `FileReader`.

See [Using files from web applications](file/using_files_from_web_applications) for details and examples.

## Properties

[`FileReader.error`](filereader/error) <span class="badge inline readonly">Read only </span>  
A [`DOMException`](domexception) representing the error that occurred while reading the file.

[`FileReader.readyState`](filereader/readystate) <span class="badge inline readonly">Read only </span>  
A number indicating the state of the `FileReader`. This is one of the following:

<table><tbody><tr class="odd"><td><code>EMPTY</code></td><td><code>0</code></td><td>No data has been loaded yet.</td></tr><tr class="even"><td><code>LOADING</code></td><td><code>1</code></td><td>Data is currently being loaded.</td></tr><tr class="odd"><td><code>DONE</code></td><td><code>2</code></td><td>The entire read request has been completed.</td></tr></tbody></table>

[`FileReader.result`](filereader/result) <span class="badge inline readonly">Read only </span>  
The file's contents. This property is only valid after the read operation is complete, and the format of the data depends on which of the methods was used to initiate the read operation.

### Event handlers

[`FileReader.onabort`](filereader/onabort)  
A handler for the `abort` event. This event is triggered each time the reading operation is aborted.

[`FileReader.onerror`](filereader/onerror)  
A handler for the `error` event. This event is triggered each time the reading operation encounter an error.

[`FileReader.onload`](filereader/onload)  
A handler for the `load` event. This event is triggered each time the reading operation is successfully completed.

<span class="page-not-created">`FileReader.onloadstart`</span>  
A handler for the `loadstart` event. This event is triggered each time the reading is starting.

<span class="page-not-created">`FileReader.onloadend`</span>  
A handler for the `loadend` event. This event is triggered each time the reading operation is completed (either in success or failure).

<span class="page-not-created">`FileReader.onprogress`</span>  
A handler for the `progress` event. This event is triggered while reading a [`Blob`](blob) content.

As `FileReader` inherits from [`EventTarget`](eventtarget), all those events can also be listened for by using the [`addEventListener`](eventtarget/addeventlistener) method.

## Methods

[`FileReader.abort()`](filereader/abort)  
Aborts the read operation. Upon return, the `readyState` will be `DONE`.

[`FileReader.readAsArrayBuffer()`](filereader/readasarraybuffer)  
Starts reading the contents of the specified [`Blob`](blob), once finished, the `result` attribute contains an [`ArrayBuffer`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer) representing the file's data.

[`FileReader.readAsBinaryString()`](filereader/readasbinarystring)  
Starts reading the contents of the specified [`Blob`](blob), once finished, the `result` attribute contains the raw binary data from the file as a string.

[`FileReader.readAsDataURL()`](filereader/readasdataurl)  
Starts reading the contents of the specified [`Blob`](blob), once finished, the `result` attribute contains a `data:` URL representing the file's data.

[`FileReader.readAsText()`](filereader/readastext)  
Starts reading the contents of the specified [`Blob`](blob), once finished, the `result` attribute contains the contents of the file as a text string. An optional encoding name can be specified.

## Events

Listen to these events using [`addEventListener()`](eventtarget/addeventlistener) or by assigning an event listener to the `oneventname` property of this interface.

[`abort`](filereader/abort_event)  
Fired when a read has been aborted, for example because the program called [`FileReader.abort()`](filereader/abort).  
Also available via the [`onabort`](filereader/onabort) property.

[`error`](filereader/error_event)  
Fired when the read failed due to an error.  
Also available via the [`onerror`](filereader/onerror) property.

[`load`](filereader/load_event)  
Fired when a read has completed successfully.  
Also available via the [`onload`](filereader/onload) property.

[`loadend`](filereader/loadend_event)  
Fired when a read has completed, successfully or not.  
Also available via the <span class="page-not-created">`onloadend`</span> property.

[`loadstart`](filereader/loadstart_event)  
Fired when a read has started.  
Also available via the <span class="page-not-created">`onloadstart`</span> property.

[`progress`](filereader/progress_event)  
Fired periodically as data is read.  
Also available via the <span class="page-not-created">`onprogress`</span> property.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/FileAPI/#dfn-filereader">File API<br />
<span class="small">The definition of 'FileReader' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`FileReader`

7

12

3.6

Prior to Firefox 4, `Blob` parameters were `File` parameters.

10

11

6

≤37

18

32

11

6

1.0

`FileReader`

7

12

3.6

10

≤12.1

6

≤37

18

32

≤12.1

6

1.0

`abort`

7

12

3.6

10

11

6

≤37

Yes

32

11

6

Yes

`abort_event`

Yes

12

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

`error`

7

12

3.6

\["Prior to Firefox 13, the `error` property returned a `FileError` object.", "From Firefox 13 to Firefox 58, the `error` property returned a `DOMError` object.", "From Firefox 58, the `error` property returns a `DOMException` object."\]

10

The `error` property returns a `DOMError` object.

11

6.1

The `error` property returns a `DOMError` object.

≤37

Yes

32

\["From Firefox 32 to Firefox 58, the `error` property returned a `DOMError` object.", "From Firefox 58, the `error` property returns a `DOMException` object."\]

11

6.1

The `error` property returns a `DOMError` object.

Yes

`error_event`

Yes

12

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

`load_event`

Yes

12

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

`loadend_event`

Yes

12

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

`loadstart_event`

Yes

12

79

Yes-79

`loadstart` event dispatches synchronously (should be asynchronously as per spec).

Yes

Yes

Yes

Yes

Yes

79

Yes-79

`loadstart` event dispatches synchronously (should be asynchronously as per spec).

Yes

Yes

Yes

`onabort`

7

12

3.6

10

11

6.1

≤37

Yes

32

11

6.1

Yes

`onerror`

7

12

3.6

10

11

6.1

≤37

Yes

32

11

6.1

Yes

`onload`

7

12

3.6

10

11

6.1

≤37

18

32

11

6.1

1.0

`onloadend`

7

12

3.6

10

11

6.1

≤37

Yes

32

11

6.1

Yes

`onprogress`

7

12

3.6

10

11

6.1

≤37

Yes

32

11

6.1

Yes

`progress_event`

Yes

12

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

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

`readAsBinaryString`

7

12

3.6

No

11

6

≤37

18

32

11

6

1.0

`readAsDataURL`

7

12

3.6

10

11

6

≤37

18

32

Using the camera in Android 8.x raises an exception. See [bug 1511083](https://bugzil.la/1511083).

11

6

1.0

`readAsText`

7

12

3.6

10

11

6

≤37

18

32

11

6

1.0

`readyState`

7

12

3.6

10

11

6.1

≤37

Yes

32

11

6.1

Yes

`result`

7

12

3.6

10

11

10

≤37

Yes

32

11

6.1

Yes

`worker_support`

Yes

≤18

46

No

11

No

Yes

Yes

46

11

No

Yes

## See also

- [Using files from web applications](file/using_files_from_web_applications)
- [`File`](file)
- [`Blob`](blob)
- [`FileReaderSync`](filereadersync)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/FileReader" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/FileReader</a>
