# FileReader.readAsBinaryString()

The `readAsBinaryString` method is used to start reading the contents of the specified [`Blob`](../blob) or [`File`](../file). When the read operation is finished, the [`readyState`](readystate) becomes `DONE`, and the `loadend` is triggered. At that time, the [`result`](result) attribute contains the raw binary data from the file.

Note that this method was once removed from the File API specification, but re-introduced for backward compatibility.  
Using [`FileReader.readAsArrayBuffer()`](readasarraybuffer) is recommended.

## Syntax

    instanceOfFileReader.readAsBinaryString(blob);

### Parameters

`blob`  
The [`Blob`](../blob) or [`File`](../file) from which to read.

## Example

    var canvas = document.createElement('canvas');
    var height = 200;
    var width  = 200;

    canvas.width  = width;
    canvas.height = height;

    var ctx = canvas.getContext('2d');

    ctx.strokeStyle = '#090';
    ctx.beginPath();
    ctx.arc(width/2, height/2, width/2 - width/10, 0, Math.PI*2);
    ctx.stroke();

    canvas.toBlob(function (blob) {
      var reader = new FileReader();

      reader.onload = function () {
        console.log(reader.result);
      }

      reader.readAsBinaryString(blob);
    });

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/FileAPI/#readAsBinaryString">File API<br />
<span class="small">The definition of 'readAsBinaryString' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

## See also

- [`FileReader`](../filereader)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/FileReader/readAsBinaryString" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/FileReader/readAsBinaryString</a>
