Event.msConvertURL()
====================

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

The `msConvertURL` method instructs the HTML paste operation on how to modify the src attribute that corresponds to each file in the clipboardData.files collection, allowing otherwise inaccessible files to be converted to blob or data URIs.

This proprietary method is specific to Internet Explorer and the Microsoft Edge browser.

Syntax
------

    var retVal = DragEvent.msConvertURL(file, targetType, targetURL);

### Parameters

**file** \[in\]

Type: *File*

The file object to be converted.

**targetType** \[in\]

Type: *DOMString*

One of the following values indicating the desired conversion type: "specified", "base64", or "unchanged".

**targetURL** \[in, optional\]

Type: *URL*

The target URL.

### Return value

This method does not return a value.

### Example

      var blobList = [];

        document.getElementById("pasteZone").addEventListener('paste', handlePaste, false);

        function handlePaste(evt) {
          var fileList = window.clipboardData.files; // Note that window.DataTransfer.files is not applicable.

          if (!fileList) {
            console.log("fileList is null.");
            return;
          }

          for (var i = 0; i < fileList.length; i++) {
            var file = fileList[i];
            var url = URL.createObjectURL(file);

            if (evt.convertURL) { // Use standard if available.
              evt.convertURL(file, "specified", url);
            } else {
              evt.msConvertURL(file, "specified", url);
            }

            console.log("Local file: " + file.name + " (" + file.size + ")");
            blobList.push(file);
          } // for
        } // handlePaste

See also
--------

-   [Microsoft API extensions](../microsoft_extensions)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Event/msConvertURL" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Event/msConvertURL</a>
