# Blob.text()

The `text()` method in the [`Blob`](../blob) interface returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with a string containing the contents of the blob, interpreted as UTF-8.

## Syntax

    var textPromise = blob.text();

    blob.text().then(text => /* do something with the text */);

    var text = await blob.text();

### Parameters

None.

### Returns

A promise that resolves with a [`USVString`](../usvstring) which contains the blob's data as a text string. The data is _always_ presumed to be in UTF-8 format.

## Usage notes

The [`FileReader`](../filereader) method [`readAsText()`](../filereader/readastext) is an older method that performs a similar function. It works on both `Blob` and [`File`](../file) objects. There are two key differences:

- `Blob.text()` returns a promise, whereas `FileReader.readAsText()` is an event based API.
- `Blob.text()` always uses UTF-8 as encoding, while `FileReader.readAsText()` can use a different encoding depending on the blob's type and a specified encoding name.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/FileAPI/#dom-blob-text">File API<br />
<span class="small">The definition of 'Blob.text()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

## See also

- [`Body.text()`](../body/text)
- [Streams API](../streams_api)
- [`FileReader.readAsText()`](../filereader/readastext)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Blob/text" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Blob/text</a>
