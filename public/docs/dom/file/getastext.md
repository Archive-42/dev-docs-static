File.getAsText()
================

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

**Note:**This method was removed from Firefox 7.0 and onward.

Summary
-------

The `getAsText` method provides the file's data interpreted as text using a given encoding.

**Note:** This method is obsolete; you should use the [`FileReader`](../filereader) method [`readAsText()`](../filereader/readastext) instead.

Syntax
------

    var str = instanceOfFile.getAsText(encoding);

### Parameters

encoding  
A string indicating the encoding to use for the returned data. If this string is empty, UTF-8 is assumed.

### Returns

A string containing the file's data interpreted as text in the specified `encoding`.

Example
-------

    // fileInput is a HTMLInputElement: <input type="file" id="myfileinput" multiple>
    var fileInput = document.getElementById("myfileinput");

    // files is a FileList object (similar to NodeList)
    var files = fileInput.files;

    // object for allowed media types
    var accept = {
      binary : ["image/png", "image/jpeg"],
      text   : ["text/plain", "text/css", "application/xml", "text/html"]
    };

    var file;

    for (var i = 0; i < files.length; i++) {
      file = files[i];

      // if file type could be detected
      if (file !== null) {
        if (accept.text.indexOf(file.mediaType) > -1) {
          // file is of type text, which we accept
          // make sure it's encoded as utf-8
          var data = file.getAsText("utf-8");
          // modify data with string methods

        } else if (accept.binary.indexOf(file.mediaType) > -1) {
          // binary
        }
      }
    }

Specifications
--------------

Not part of any specification.

See also
--------

-   [`File`](../file)
-   [`FileReader`](../filereader)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/File/getAsText" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/File/getAsText</a>
