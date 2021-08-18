File
====

The `File` interface provides information about files and allows JavaScript in a web page to access their content.

`File` objects are generally retrieved from a [`FileList`](filelist) object returned as a result of a user selecting files using the [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input) element, from a drag and drop operation's [`DataTransfer`](datatransfer) object, or from the `mozGetAsFile()` API on an [`HTMLCanvasElement`](htmlcanvaselement).

A `File` object is a specific kind of a [`Blob`](blob), and can be used in any context that a Blob can. In particular, [`FileReader`](filereader), [`URL.createObjectURL()`](url/createobjecturl), [`createImageBitmap()`](windoworworkerglobalscope/createimagebitmap), and [`XMLHttpRequest.send()`](xmlhttprequest#send()) accept both `Blob`s and `File`s.

See [Using files from web applications](file/using_files_from_web_applications) for more information and examples.

Constructor
-----------

[`File()`](file/file)  
Returns a newly constructed `File`.

Instance properties
-------------------

 [`File.prototype.lastModified`](file/lastmodified) <span class="badge inline readonly">Read only </span>   
Returns the last modified time of the file, in millisecond since the UNIX epoch (January 1st, 1970 at Midnight).

 [`File.prototype.lastModifiedDate`](file/lastmodifieddate) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span> <span class="badge inline readonly">Read only </span>   
Returns the last modified [`Date`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date) of the file referenced by the `File` object.

 [`File.prototype.name`](file/name)<span class="badge inline readonly">Read only </span>   
Returns the name of the file referenced by the `File` object.

 [`File.prototype.webkitRelativePath`](file/webkitrelativepath) <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span> <span class="badge inline readonly">Read only </span>   
Returns the path the URL of the [`File`](file) is relative to.

`File` implements [`Blob`](blob), so it also has the following properties available to it:

 [`File.prototype.size`](file/size) <span class="badge inline readonly">Read only </span>   
Returns the size of the file in bytes.

 [`File.prototype.type`](file/type) <span class="badge inline readonly">Read only </span>   
Returns the [MIME](https://developer.mozilla.org/en-US/docs/Web/HTTP/Basics_of_HTTP/MIME_types) type of the file.

Instance methods
----------------

*The `File` interface doesn't define any methods, but inherits methods from the [`Blob`](blob) interface:*

[`Blob.prototype.slice([start[, end[, contentType]]])`](blob/slice)  
Returns a new `Blob` object containing the data in the specified range of bytes of the source `Blob`.

[`Blob.prototype.stream()`](blob/stream)  
Transforms the `File` into a [`ReadableStream`](readablestream) that can be used to read the `File` contents.

[`Blob.prototype.text()`](blob/text)  
Transforms the `File` into a stream and reads it to completion. It returns a promise that resolves with a [`USVString`](usvstring) (text).

[`Blob.prototype.arrayBuffer()`](blob/arraybuffer)  
Transforms the `File` into a stream and reads it to completion. It returns a promise that resolves with an [`ArrayBuffer`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer).

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/FileAPI/#file-section">File API<br />
<span class="small">The definition of 'The <code>File</code> interface' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`File`

13

12

7

3-7

Non-standard implementation.

10

11.5

4

≤37

18

7

4-7

Non-standard implementation.

11.5

3.2

1.0

`File`

38

79

28

No

25

10

38

38

28

25

10

3.0

`lastModified`

13

18

15

No

16

10

≤37

Yes

No

No

10

Yes

`lastModifiedDate`

13

12

15-61

10

16

6.1-10

≤37

Yes

No

No

7-10

Yes

`name`

13

12

3.6

10

16

6.1

≤37

Yes

4

No

7

Yes

`type`

13

12

3.6

10

16

6.1

≤37

Yes

No

No

7

Yes

`webkitRelativePath`

13

13

49

No

No

11.1

≤37

18

49

No

11.3

1.0

See also
--------

-   [Using files from web applications](file/using_files_from_web_applications)
-   [`FileReader`](filereader)
-   [Using the DOM File API in chrome code](https://developer.mozilla.org/en-US/docs/Extensions/Using_the_DOM_File_API_in_chrome_code) (for privileged code running in Gecko, such as Firefox add-ons)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/File" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/File</a>
