# File.type

Returns the media type ([MIME](https://developer.mozilla.org/en-US/docs/Web/HTTP/Basics_of_HTTP/MIME_types)) of the file represented by a [`File`](../file) object.

## Syntax

    var name = file.type;

## Value

A string, containing the media type(MIME) indicating the type of the file, for example "image/png" for PNG images

## Example

    <input type="file" multiple onchange="showType(this)">

    function showType(fileInput) {
      var files = fileInput.files;

      for (var i = 0; i < files.length; i++) {
        var name = files[i].name;
        var type = files[i].type;
        alert("Filename: " + name + " , Type: " + type);
      }
    }

**Note:** Based on the current implementation, browsers won't actually read the bytestream of a file to determine its media type. It is assumed based on the file extension; a PNG image file renamed to .txt would give "_text/plain_" and not "_image/png_". Moreover, `file.type` is generally reliable only for common file types like images, HTML documents, audio and video. Uncommon file extensions would return an empty string. Client configuration (for instance, the Windows Registry) may result in unexpected values even for common types. **Developers are advised not to rely on this property as a sole validation scheme.**

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/FileAPI/#dfn-type">File API<br />
<span class="small">The definition of 'type' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

## See also

- [Using files from web applications](using_files_from_web_applications)
- Blog Post: [Be skeptical of client-reported MIME types](https://textslashplain.com/2018/07/26/be-skeptical-of-client-reported-mime-content-types/)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/File/type" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/File/type</a>
