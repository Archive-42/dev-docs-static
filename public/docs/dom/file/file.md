# File.File()

The `File()` constructor creates a new [`File`](../file) object instance.

## Syntax

    new File(bits, name[, options]);

### Parameters

`bits`  
An [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) of [`ArrayBuffer`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer), [`ArrayBufferView`](../arraybufferview), [`Blob`](../blob), [`USVString`](../usvstring) objects, or a mix of any of such objects, that will be put inside the [`File`](../file). `USVString` objects are encoded as UTF-8.

`name`  
A [`USVString`](../usvstring) representing the file name or the path to the file.

`options` <span class="badge inline optional">Optional</span>  
An options object containing optional attributes for the file. Available options are as follows:

- `type`: A [`DOMString`](../domstring) representing the MIME type of the content that will be put into the file. Defaults to a value of `"".`
- `lastModified`: A number representing the number of milliseconds between the Unix time epoch and when the file was last modified. Defaults to a value of [`Date.now()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date/now).

## Example

    var file = new File(["foo"], "foo.txt", {
      type: "text/plain",
    });

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/FileAPI/">File API</a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

## See also

- [`FileReader`](../filereader)
- [`Blob`](../blob)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/File/File" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/File/File</a>
