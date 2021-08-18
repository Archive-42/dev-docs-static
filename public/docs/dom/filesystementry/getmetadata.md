# FileSystemEntry.getMetadata()

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The [`FileSystemEntry`](../filesystementry) interface's method ` getMetadata``() ` obtains a [`Metadata`](../metadata) object with information about the file system entry, such as its modification date and time and its size.

## Syntax

    FileSystemEntry.getMetadata(successCallback[, errorCallback]);

### Parameters

`successCallback`  
A function which is called when the copy operation is successfully completed. Receives a single input parameter: a [`Metadata`](../metadata) object with information about the file.

`errorCallback` <span class="badge inline optional">Optional</span>  
An optional callback which is executed if an error occurs while looking up the metadata. There's a single parameter: a [`FileError`](../fileerror) describing what went wrong.

### Return value

[`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined).

### Errors

`FileError.NOT_FOUND_ERR`  
The [`FileSystemEntry`](../filesystementry) refers to an item which doesn't exist.

`FileError.SECURITY_ERR`  
Security restrictions prohibit obtaining the requested metadata.

## Example

This example checks the size of a log file in a temporary folder and, if it exceeds a megabyte, moves it into a different directory.

    workingDirectory.getFile("tmp/log.txt", {}, function(fileEntry) {
      fileEntry.getMetadata(function(metadata) {
        if (metadata.size > 1048576) {
          workingDirectory.getDirectory("log", {}, function(dirEntry) {
            fileEntry.moveTo(dirEntry);
          }, handleError);
        }
      });
    }, handleError);

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

`getMetadata`

8

79

No

No

No

No

≤37

18

No

No

No

1.0

## See also

- [File and Directory Entries API](../file_and_directory_entries_api)
- [Introduction to the File System API](../file_and_directory_entries_api/introduction)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/FileSystemEntry/getMetadata" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/FileSystemEntry/getMetadata</a>
