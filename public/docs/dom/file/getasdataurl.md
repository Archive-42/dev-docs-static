File.getAsDataURL()
===================

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

Summary
-------

The getAsDataURL provides a [`data:`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Basics_of_HTTP/Data_URIs) URL that encodes the entire contents of the referenced file.

**Note:** This method is obsolete; you should use the [`FileReader`](../filereader) method [`readAsDataURL()`](../filereader/readasdataurl) instead.

Syntax
------

    var url = instanceOfFile.getAsDataURL();

### Returns

A string representing a [`data:`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Basics_of_HTTP/Data_URIs) URL

Example
-------

    // fileInput is a HTMLInputElement: <input type="file" id="myfileinput" multiple>
    var fileInput = document.getElementById("myfileinput");

    // files is a FileList object (similar to NodeList)
    var files = fileInput.files;

    // array with acceptable file types
    var accept = ["image/png"];

    // img is a HTMLImgElement: <img id="myimg">
    var img = document.getElementById("myimg");

    // if we accept the first selected file type
    if (accept.indexOf(files[0].mediaType) > -1) {
      // display the image
      // same as <img src="data:image/png,<imagedata>">
      img.src = files[0].getAsDataURL();
    }

Specifications
--------------

Not part of any specification.

See also
--------

-   [`File`](../file)
-   [`FileReader`](../filereader)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/File/getAsDataURL" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/File/getAsDataURL</a>
