# FileReader.readAsDataURL()

The `readAsDataURL` method is used to read the contents of the specified [`Blob`](../blob) or [`File`](../file). When the read operation is finished, the [`readyState`](readystate) becomes `DONE`, and the `loadend` is triggered. At that time, the [`result`](result) attribute contains the data as a [data: URL](https://developer.mozilla.org/en-US/docs/Web/HTTP/Basics_of_HTTP/Data_URIs) representing the file's data as a base64 encoded string.

**Note:** The blob's [`result`](result) cannot be directly decoded as Base64 without first removing the Data-URL declaration preceding the Base64-encoded data. To retrieve only the Base64 encoded string, first remove `data:*/*;base64,` from the result.

## Syntax

    instanceOfFileReader.readAsDataURL(blob);

### Parameters

`blob`  
The [`Blob`](../blob) or [`File`](../file) from which to read.

## Example

### HTML

    <input type="file" onchange="previewFile()"><br>
    <img src="" height="200" alt="Image preview...">

### JavaScript

    function previewFile() {
      const preview = document.querySelector('img');
      const file = document.querySelector('input[type=file]').files[0];
      const reader = new FileReader();

      reader.addEventListener("load", function () {
        // convert image file to base64 string
        preview.src = reader.result;
      }, false);

      if (file) {
        reader.readAsDataURL(file);
      }
    }

### Live Result

## Example reading multiple files

### HTML

    <input id="browse" type="file" onchange="previewFiles()" multiple>
    <div id="preview"></div>

### JavaScript

    function previewFiles() {

      var preview = document.querySelector('#preview');
      var files   = document.querySelector('input[type=file]').files;

      function readAndPreview(file) {

        // Make sure `file.name` matches our extensions criteria
        if ( /\.(jpe?g|png|gif)$/i.test(file.name) ) {
          var reader = new FileReader();

          reader.addEventListener("load", function () {
            var image = new Image();
            image.height = 100;
            image.title = file.name;
            image.src = this.result;
            preview.appendChild( image );
          }, false);

          reader.readAsDataURL(file);
        }

      }

      if (files) {
        [].forEach.call(files, readAndPreview);
      }

    }

**Note:** The [`FileReader()`](../filereader) constructor was not supported by Internet Explorer for versions before 10. For a full compatibility code you can see our [crossbrowser possible solution for image preview](https://mdn.mozillademos.org/files/3699/crossbrowser_image_preview.html). See also [this more powerful example](https://mdn.mozillademos.org/files/3698/image_upload_preview.html).

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/FileAPI/#readAsDataURL">File API<br />
<span class="small">The definition of 'readAsDataURL()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

## See also

- [`FileReader`](../filereader)
- [`URL.createObjectURL()`](../url/createobjecturl)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/FileReader/readAsDataURL" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/FileReader/readAsDataURL</a>
