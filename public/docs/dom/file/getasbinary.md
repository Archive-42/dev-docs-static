# File.getAsBinary()

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

**Note:**This method was removed from Firefox 7.0 and onward.

## Summary

The `getAsBinary` method allows to access the file's data in raw binary format.

**Note:** This method is obsolete; you should use the [`FileReader`](../filereader) method [`readAsBinaryString()`](../filereader/readasbinarystring) or [`readAsArrayBuffer()`](../filereader/readasarraybuffer) instead.

## Syntax

    var binary = instanceOfFile.getAsBinary();

### Returns

A string.

## Example

    // fileInput is an HTMLInputElement: <input type="file" id="myfileinput" multiple>
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
        if (accept.binary.indexOf(file.type) > -1) {
          // file is a binary, which we accept
          var data = file.getAsBinary();
        } else if (accept.text.indexOf(file.type) > -1) {
          // file is of type text, which we accept
          var data = file.getAsText();
          // modify data with string methods
        }
      }
    }

## Specifications

Not part of any specification.

## See also

- [`File`](../file)
- [`FileReader`](../filereader)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/File/getAsBinary" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/File/getAsBinary</a>
