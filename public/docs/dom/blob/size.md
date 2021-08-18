# Blob.size

The [`Blob`](../blob) interface's `size` property returns the size of the [`Blob`](../blob) or [`File`](../file) in bytes.

## Syntax

    var sizeInBytes = blob.size

### Value

The number of bytes of data contained within the `Blob` (or `Blob`-based object, such as a [`File`](../file)).

## Example

This example uses an [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input) element of type `file` to ask the user for a group of files, then iterates over those files outputting their names and lengths in bytes.

    // fileInput is a HTMLInputElement: <input type="file" multiple id="myfileinput">
    var fileInput = document.getElementById("myfileinput");

    // files is a FileList object (similar to NodeList)
    var files = fileInput.files;

    for (var i = 0; i < files.length; i++) {
      console.log(files[i].name + " has a size of " + files[i].size + " Bytes");
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/FileAPI/#dfn-size">File API<br />
<span class="small">The definition of 'Blob.size' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

## See also

- [`Blob`](../blob)
- [Using files from web applications](../file/using_files_from_web_applications)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Blob/size" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Blob/size</a>
