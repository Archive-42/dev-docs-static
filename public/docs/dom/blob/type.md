# Blob.type

The `type` property of a [`Blob`](../blob) object returns the [MIME type](https://developer.mozilla.org/en-US/docs/Glossary/MIME_type) of the file.

## Syntax

    var mimetype = blob.type

### Value

A [`DOMString`](../domstring) containing the file's MIME type, or an empty string if the type could not be determined.

## Example

This example asks the user to select a number of files, then checks each file to make sure it's one of a given set of image file types.

    var i, fileInput, files, allowedFileTypes;

    // fileInput is a HTMLInputElement: <input type="file" multiple id="myfileinput">
    fileInput = document.getElementById("myfileinput");

    // files is a FileList object (similar to NodeList)
    files = fileInput.files;

    // our application only allows GIF, PNG, and JPEG images
    allowedFileTypes = ["image/png", "image/jpeg", "image/gif"];

    for (i = 0; i < files.length; i++) {
      // Test if file.type is an allowed file type.
      if (allowedFileTypes.indexOf(files[i].type) > -1) {
        // file type matched is one of allowed file types. Do something here.
      }
    });

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/FileAPI/#dfn-type">File API<br />
<span class="small">The definition of 'Blob.type' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

- [`Blob`](../blob)
- [Using files from web applications](../file/using_files_from_web_applications)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Blob/type" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Blob/type</a>
