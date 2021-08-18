FileSystemEntry.copyTo()
========================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The [`FileSystemEntry`](../filesystementry) interface's method `copyTo``()` copies the file specified by the entry to a new location on the file system. There are some typical restrictions on what you can do:

-   A directory can't be copied into itself.
-   An entry can't be copied into its parent directory unless you specify a new name.
-   When copying a directory, the copy is always recursive; you can't leave out subfolders.

Syntax
------

    FileSystemEntry.copyTo(newParent[, newName][, successCallback][, errorCallback]);

### Parameters

`newParent`  
A [`FileSystemDirectoryEntry`](../filesystemdirectoryentry) object specifying the destination directory for the copy operation.

 `newName` <span class="badge inline optional">Optional</span>   
If this parameter is provided, the copy is given this string as its new file or directory name.

 `successCallback` <span class="badge inline optional">Optional</span>   
A function which is called when the copy operation is successfully completed. Receives a single input parameter: a [`FileSystemEntry`](../filesystementry) based object providing the copied item's new details.

 `errorCallback` <span class="badge inline optional">Optional</span>   
An optional callback which is executed if an error occurs while copying the items. There's a single parameter: a [`FileError`](../fileerror) describing what went wrong.

### Return value

[`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined).

### Errors

`FileError.INVALID_MODIFICATION_ERR`  
The requested operation involves an impossible change, such as moving a directory inside itself or one of its own child directories, or copying an item within the same directory without renaming it.

`FileError.QUOTA_EXCEEDED_ERR`  
The operation exceeded the user's storage quota, or there isn't enough storage space left to complete the operation.

Example
-------

This example shows how a temporary log file might be moved into a more permanent "log" directory.

    workingDirectory.getFile("tmp/log.txt", {}, function(fileEntry) {
      workingDirectory.getDirectory("log", {}, function(dirEntry) {
        fileEntry.copyTo(dirEntry);
      }, handleError);
    }, handleError);

Browser compatibility
---------------------

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

`copyTo`

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

See also
--------

-   [File and Directory Entries API](../file_and_directory_entries_api)
-   [Introduction to the File System API](../file_and_directory_entries_api/introduction)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/FileSystemEntry/copyTo" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/FileSystemEntry/copyTo</a>
