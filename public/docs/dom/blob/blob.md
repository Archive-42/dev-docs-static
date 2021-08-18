# Blob()

The `Blob()` constructor returns a new [`Blob`](../blob) object. The content of the blob consists of the concatenation of the values given in the parameter `array`.

## Syntax

    var newBlob = new Blob(array, options);

### Parameters

`array`  
An [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) of [`ArrayBuffer`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer), [`ArrayBufferView`](../arraybufferview), [`Blob`](../blob), [`USVString`](../usvstring) objects, or a mix of any of such objects, that will be put inside the [`Blob`](../blob). `USVString` objects are encoded as UTF-8.

`options` <span class="badge inline optional">Optional</span>  
An optional object of type <span class="page-not-created">`BlobPropertyBag`</span> which may specify any of the following properties:

`type` <span class="badge inline optional">Optional</span>  
The [MIME type](https://developer.mozilla.org/en-US/docs/Glossary/MIME_type) of the data that will be stored into the blob. The default value is the empty string, (`""`).

`endings` <span class="badge inline optional">Optional</span> <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>  
How to interpret newline characters (`\n`) within the contents, if the data is text. The default value, `transparent`, copies newline characters into the blob without changing them. To convert newlines to the host system's native convention, specify the value `native`.

### Return value

A new [`Blob`](../blob) object containing the specified data.

## Example

    var aFileParts = ['<a id="a"><b id="b">hey!</b></a>']; // an array consisting of a single DOMString
    var oMyBlob = new Blob(aFileParts, {type : 'text/html'}); // the blob

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/FileAPI/#constructorBlob">File API<br />
<span class="small">The definition of 'Blob()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

## See also

- The deprecated [`BlobBuilder`](../blobbuilder) interface which this constructor replaces.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Blob/Blob" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Blob/Blob</a>
