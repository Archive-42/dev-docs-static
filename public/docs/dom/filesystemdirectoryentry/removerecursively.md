# FileSystemDirectoryEntry.removeRecursively()

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The [`FileSystemDirectoryEntry`](../filesystemdirectoryentry) interface's method ` removeRecursively``() ` removes the directory as well as all of its content, hierarchically iterating over its entire subtree of descendant files and directories.

To remove a single file, or an empty directory, you can also use [`FileSystemEntry.remove()`](../filesystementry/remove).

## Syntax

    FileSystemDirectoryEntry.removeRecursively(successCallback[, errorCallback]);

### Parameters

`successCallback`  
A function to call once the directory removal process has completed. The callback has no parameters.

`errorCallback` <span class="badge inline optional">Optional</span>  
A function to be called if an error occurs while attempting to remove the directory subtree. Receives a [`FileError`](../fileerror) describing the error which occurred as input.

### Return value

[`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined).

### Errors

If an error occurs and an `errorCallback` was specified, it gets called with a single parameter: a [`FileError`](../fileerror) object describing the error. The <span class="page-not-created">`FileError.code`</span> specifies what type of error occurred, as follows:

`FileError.INVALID_MODIFICATION_ERR`  
An attempt was made to remove the root directory; this is not permitted.

`FileError.NO_MODIFICATION_ALLOWED_ERR`  
The file system's state doesn't permit modification.

`FileError.NOT_FOUND_ERR`  
The directory represented by the [`FileSystemDirectoryEntry`](../filesystemdirectoryentry) no longer exists.

`FileError.NOT_READABLE_ERR`  
The directory is not accessible; perhaps it's in use by another application or is locked at the operating system level.

`FileError.SECURITY_ERR`  
The directory could not be removed for security reasons. Possible reasons include:

- The directory and/or its contents may not be safe to access from a Web application.
- Too many file system calls are being made.
- Other security concerns as raised by the user agent or the operating system.

If you try to delete a directory which contains one or more files that can't be removed, or if an error occurs while deletion of a number of files is underway, some files may not be deleted. You should provide an `errorCallback` to watch for and handle this, perhaps by trying again.

## Example

    directory.removeRecursively(function() {
      /* The directory was removed successfully */
    }, function() {
      /* an error occurred while removing the directory */
    });

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

`removeRecursively`

8

79

50-52

While the `removeRecursively()` method existed, it immediately called the error callback with `NS_ERROR_DOM_SECURITY_ERR`.

No

No

No

≤37

18

50-52

While the `removeRecursively()` method existed, it immediately called the error callback with `NS_ERROR_DOM_SECURITY_ERR`.

No

No

1.0

## See also

- [File and Directory Entries API](../file_and_directory_entries_api)
- [Introduction to the File System API](../file_and_directory_entries_api/introduction)
- [`FileSystemDirectoryEntry`](../filesystemdirectoryentry)
- [`FileSystemEntry.remove()`](../filesystementry/remove)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/FileSystemDirectoryEntry/removeRecursively" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/FileSystemDirectoryEntry/removeRecursively</a>
