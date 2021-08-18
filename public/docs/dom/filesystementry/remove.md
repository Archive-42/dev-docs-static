FileSystemEntry.remove()
========================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The [`FileSystemEntry`](../filesystementry) interface's method `remove``()` deletes the file or directory from the file system. Directories must be empty before they can be removed.

To recursively remove a directory as well as all of its contents and its subdirectories, call [`FileSystemDirectoryEntry.removeRecursively()`](../filesystemdirectoryentry/removerecursively) instead.

Syntax
------

    FileSystemEntry.remove(successCallback[, errorCallback]);

### Parameters

`successCallback`  
A function which is called once the file has been successfully removed.

 `errorCallback` <span class="badge inline optional">Optional</span>   
An optional callback which is called if the attempt to remove the file fails.

### Return value

[`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined).

### Errors

`FileError.INVALID_MODIFICATION_ERR`  
The specified entry was the file system's root directory, or the specified entry is a directory which isn't empty.

`FileError.INVALID_STATE_ERR`  
The file system's cached state is inconsistent with its state on disk, so the file could not be deleted for safety reasons.

`FileError.NO_MODIFICATION_ALLOWED_ERR`  
The file system's state doesn't permit removing the file or directory.

`FileError.NOT_FOUND_ERR`  
The file or directory doesn't exist.

`FileError.SECURITY_ERR`  
The entry couldn't be removed due to permissions or other access constraints, or because there are too many calls being made on file resources.

Example
-------

This example deletes a temporary work file.

    workingDirectory.getFile("tmp/workfile.json", {}, function(fileEntry) {
      fileEntry.remove(function() {
        /* the file was removed successfully */
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

`remove`

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
-   [`FileSystemDirectoryEntry.removeRecursively()`](../filesystemdirectoryentry/removerecursively)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/FileSystemEntry/remove" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/FileSystemEntry/remove</a>
