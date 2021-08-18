# Blob

The `Blob` object represents a blob, which is a file-like object of immutable, raw data; they can be read as text or binary data, or converted into a [`ReadableStream`](readablestream) so its methods can be used for processing the data.

Blobs can represent data that isn't necessarily in a JavaScript-native format. The [`File`](file) interface is based on `Blob`, inheriting blob functionality and expanding it to support files on the user's system.

## Using blobs

To construct a `Blob` from other non-blob objects and data, use the [`Blob()`](blob/blob) constructor. To create a blob that contains a subset of another blob's data, use the [`slice()`](blob/slice) method. To obtain a `Blob` object for a file on the user's file system, see the [`File`](file) documentation.

The APIs accepting `Blob` objects are also listed in the [`File`](file) documentation.

## Constructor

[`Blob()`](blob/blob)  
Returns a newly created `Blob` object which contains a concatenation of all of the data in the array passed into the constructor.

## Instance properties

[`Blob.prototype.size`](blob/size) <span class="badge inline readonly">Read only </span>  
The size, in bytes, of the data contained in the `Blob` object.

[`Blob.prototype.type`](blob/type) <span class="badge inline readonly">Read only </span>  
A string indicating the MIME type of the data contained in the `Blob`. If the type is unknown, this string is empty.

## Instance methods

[`Blob.prototype.arrayBuffer()`](blob/arraybuffer)  
Returns a promise that resolves with an [`ArrayBuffer`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer) containing the entire contents of the `Blob` as binary data.

[`Blob.prototype.slice()`](blob/slice)  
Returns a new `Blob` object containing the data in the specified range of bytes of the blob on which it's called.

[`Blob.prototype.stream()`](blob/stream)  
Returns a [`ReadableStream`](readablestream) that can be used to read the contents of the `Blob`.

[`Blob.prototype.text()`](blob/text)  
Returns a promise that resolves with a [`USVString`](usvstring) containing the entire contents of the `Blob` interpreted as UTF-8 text.

## Examples

### Creating a blob

The [`Blob()`](blob/blob) constructor can create blobs from other objects. For example, to construct a blob from a JSON string:

    const obj = {hello: 'world'};
    const blob = new Blob([JSON.stringify(obj, null, 2)], {type : 'application/json'});

### Creating a URL representing the contents of a typed array

The following code creates a JavaScript [typed array](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Typed_arrays) and creates a new `Blob` containing the typed array's data. It then calls [`URL.createObjectURL()`](url/createobjecturl) to convert the blob into a [URL](https://developer.mozilla.org/en-US/docs/Glossary/URL).

#### HTML

    <p>This example creates a typed array containing the ASCII codes
       for the space character through the letter Z, then converts it
       to an object URL. A link to open that object URL is created.
       Click the link to see the decoded object URL.</p>

#### JavaScript

The main piece of this code for example purposes is the `typedArrayToURL()` function, which creates a `Blob` from the given typed array and returns an object URL for it. Having converted the data into an object URL, it can be used in a number of ways, including as the value of the [`<img>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img) element's [`src`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img#attr-src) attribute (assuming the data contains an image, of course).

    function typedArrayToURL(typedArray, mimeType) {
      return URL.createObjectURL(new Blob([typedArray.buffer], {type: mimeType}))
    }

    const bytes = new Uint8Array(59);

    for(let i = 0; i < 59; i++) {
      bytes[i] = 32 + i;
    }

    const url = typedArrayToURL(bytes, 'text/plain');

    const link = document.createElement('a');
    link.href = url;
    link.innerText = 'Open the array URL';

    document.body.appendChild(link);

#### Result

Click the link in the example to see the browser decode the object URL.

### Extracting data from a blob

One way to read content from a `Blob` is to use a [`FileReader`](filereader). The following code reads the content of a `Blob` as a typed array:

    const reader = new FileReader();
    reader.addEventListener('loadend', () => {
       // reader.result contains the contents of blob as a typed array
    });
    reader.readAsArrayBuffer(blob);

Another way to read content from a `Blob` is to use a [`Response`](response). The following code reads the content of a `Blob` as text:

    const text = await (new Response(blob)).text();

Or by using [`Blob.prototype.text()`](blob/text):

    const text = await blob.text();

By using other methods of `FileReader`, it is possible to read the contents of a Blob as a string or a data URL.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/FileAPI/#blob-section">File API<br />
<span class="small">The definition of 'The <code>Blob</code> interface' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`Blob`

5

12

4

10

11

5.1

≤37

18

14

11

6

1.0

`Blob`

20

12

13

Before Firefox 16, the second parameter, when set to `null` or `undefined`, leads to an error instead of being handled as an empty dictionary.

10

12

8

37

25

14

Before Firefox 16, the second parameter, when set to `null` or `undefined`, leads to an error instead of being handled as an empty dictionary.

12

8

1.5

`arrayBuffer`

76

79

69

No

No

14

76

76

No

54

14

12.0

`size`

5

12

4

10

11

5.1

≤37

18

No

No

No

1.0

`slice`

21

5-25

12

13

Prior to Firefox 12, there was a bug that affected the behavior of `Blob.slice()`; it did not work for `start` and `end` positions outside the range of signed 64-bit values; it has now been fixed to support unsigned 64-bit values.

5-13

10

12

5.1

≤37

25

18-25

14

Yes

Yes

1.5

1.0-1.5

`stream`

76

79

69

No

No

14.1

76

76

No

54

14.5

12.0

`text`

76

79

69

No

63

14

76

76

No

54

14

12.0

`type`

5

12

4

10

11

5.1

≤37

18

No

No

No

1.0

## See also

- [`BlobBuilder`](blobbuilder)
- [`FileReader`](filereader)
- [`File`](file)
- [`URL.createObjectURL`](url/createobjecturl)
- [Using files from web applications](file/using_files_from_web_applications)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Blob" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Blob</a>
