FileSystemEntry.moveTo()
========================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The [`FileSystemEntry`](../filesystementry) interface's method `moveTo``()` moves the file specified by the entry to a new location on the file system, or renames the file if the destination directory is the same as the source. There are some typical restrictions on what you can do:

-   A directory can't be moved into itself.
-   An entry can't be moved into its parent directory unless you specify a new name. Specifying a new name lets `moveTo()` double as a rename operation.
-   When moving a directory, the move is always recursive; you can't leave out subfolders.
-   You can't move a file such that it replaces an existing directory, and you can't move a directory such that it replaces an existing file. However, a file can replace a file and a directory can replace a directory.
-   You can only overwrite a directory if it's empty.

Syntax
------

    FileSystemEntry.moveTo(newParent[, newName][, successCallback][, errorCallback]);

### Parameters

`newParent`  
A [`FileSystemDirectoryEntry`](../filesystemdirectoryentry) object specifying the destination directory for the move operation.

 `newName` <span class="badge inline optional">Optional</span>   
If this parameter is provided, the entry is renamed to have this string as its new file or directory name.

 `successCallback` <span class="badge inline optional">Optional</span>   
A function which is called when the move operation is successfully completed. Receives a single input parameter: a [`FileSystemEntry`](../filesystementry) based object providing the moved item's new details.

 `errorCallback` <span class="badge inline optional">Optional</span>   
An optional callback which is executed if an error occurs while moving the items. There's a single parameter: a [`FileError`](../fileerror) describing what went wrong.

### Return value

[`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined).

### Errors

`FileError.INVALID_MODIFICATION_ERR`  
The requested operation involves an impossible change, such as moving a directory inside itself or one of its own child directories, or copying an item within the same directory without renaming it.

`FileError.QUOTA_EXCEEDED_ERR`  
The operation exceeded the user's storage quota, or there isn't enough storage space left to complete the operation.

Example
-------

This example shows how a temporary log file might be moved into a more permanent "log" directory when it exceeds a megabyte in size.

    workingDirectory.getFile("tmp/log.txt", {}, function(fileEntry) {
      fileEntry.getMetadata(function(metadata) {
        if (metadata.size > 1048576) {
          workingDirectory.getDirectory("log", {}, function(dirEntry) {
            fileEntry.moveTo(dirEntry);
          }, handleError);
        }
      });
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

`moveTo`

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
-   [`FileSystemEntry.copyTo()`](copyto)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/FileSystemEntry/moveTo" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/FileSystemEntry/moveTo</a>
