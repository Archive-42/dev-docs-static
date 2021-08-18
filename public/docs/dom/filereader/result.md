# FileReader.result

The [`FileReader`](../filereader) `result` property returns the file's contents. This property is only valid after the read operation is complete, and the format of the data depends on which of the methods was used to initiate the read operation.

## Syntax

    var file = instanceOfFileReader.result

### Value

An appropriate string or [`ArrayBuffer`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer) based on which of the reading methods was used to initiate the read operation. The value is `null` if the reading is not yet complete or was unsuccessful.

The result types are described below.

<table><thead><tr class="header"><th>Method</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><a href="readasarraybuffer"><code>readAsArrayBuffer()</code></a></td><td>The <code>result</code> is a JavaScript <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer"><code>ArrayBuffer</code></a> containing binary data.</td></tr><tr class="even"><td><a href="readasbinarystring"><code>readAsBinaryString()</code></a></td><td>The <code>result</code> contains the raw binary data from the file in a string.</td></tr><tr class="odd"><td><a href="readasdataurl"><code>readAsDataURL()</code></a></td><td>The <code>result</code> is a string with a <code>data:</code> URL representing the file's data.</td></tr><tr class="even"><td><a href="readastext"><code>readAsText()</code></a></td><td>The <code>result</code> is text in a string.</td></tr></tbody></table>

## Example

This example presents a function, `read()`, which reads a file from a [file input](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/file). It works by creating a [`FileReader`](../filereader) object and creating a listener for [`load`](load_event) events such that when then file is read, the `result` is obtained and passed to the callback function provided to `read()`.

The content is handled as raw text data.

    var fileInput = document.querySelector('input[type="file"]');

    function read(callback) {
      var file = fileInput.files.item(0);
      var reader = new FileReader();

      reader.onload = function() {
        callback(reader.result);
      }

      reader.readAsText(file);
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/FileAPI/#dom-filereader-result">File API<br />
<span class="small">The definition of 'result' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

## See also

- [`FileReader`](../filereader)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/FileReader/result" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/FileReader/result</a>
