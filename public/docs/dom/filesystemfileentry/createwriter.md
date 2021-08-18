# FileSystemFileEntry.createWriter()

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

The [`FileSystemFileEntry`](../filesystemfileentry) interface's method `createWriter()` returns a <span class="page-not-created">`FileWriter`</span> object which can be used to write data into the file represented by the directory entry.

## Syntax

    FileSystemFileEntry.createWriter(successCallback[, errorCallback]);

### Parameters

`successCallback`  
A callback function which is called when the <span class="page-not-created">`FileWriter`</span> has been created successfully; the `FileWriter` is passed into the callback as the only parameter.

`errorCallback` <span class="badge inline optional">Optional</span>  
If provided, this must be a method which is called when an error occurs while trying to create the <span class="page-not-created">`FileWriter`</span>. This callback receives as input a [`FileError`](../fileerror) object describing the error.

### Return value

[`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined).

## Example

This example establishes a method, `writeToFileEntry()`, which outputs a text string to the file corresponding to the passed-in directory entry.

    function writeToFileEntry(entry, text) {
      entry.createWriter(function(fileWriter) {
        let data = Blob([text], { type: "text/plain" });

        fileWriter.write(data);
      }, function(fileError) {
        /* do whatever to handle the error */
      });
    }

The success callback for the `createWriter()` call takes the text which was passed in and creates a new [`Blob`](../blob) object of type `text/plain` that contains the passed text. This blob is then output to the <span class="page-not-created">`FileWriter`</span> object to be written to the file.

This API has no official W3C or WHATWG specification.

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

`createWriter`

8

79

50-52

While the `createWriter()` method existed, it immediately called `errorCallback` with the `NS_ERROR_DOM_SECURITY_ERR` error.

No

No

No

≤37

18

50-52

While the `createWriter()` method existed, it immediately called `errorCallback` with the `NS_ERROR_DOM_SECURITY_ERR` error.

No

No

1.0

## See also

- [File and Directory Entries API](../file_and_directory_entries_api)
- [Introduction to the File System API](../file_and_directory_entries_api/introduction)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/FileSystemFileEntry/createWriter" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/FileSystemFileEntry/createWriter</a>
