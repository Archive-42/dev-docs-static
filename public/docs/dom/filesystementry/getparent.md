FileSystemEntry.getParent()
===========================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The [`FileSystemEntry`](../filesystementry) interface's method `getParent``()` obtains a [`FileSystemDirectoryEntry`](../filesystemdirectoryentry).

Syntax
------

    FileSystemEntry.getParent(successCallback[, errorCallback]);

### Parameters

`successCallback`  
A function which is called when the parent directory entry has been retrieved. The callback receives a single input parameter: a [`FileSystemDirectoryEntry`](../filesystemdirectoryentry) object representing the parent directory. The parent of the root directory is considered to be the root directory, itself, so be sure to watch for that.

 `errorCallback` <span class="badge inline optional">Optional</span>   
An optional callback which is executed if an error occurs. There's a single parameter: a [`FileError`](../fileerror) describing what went wrong.

### Return value

[`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined).

### Errors

`FileError.INVALID_STATE_ERR`  
The operation failed because the file system's state doesn't permit it. This can happen, for example, if the file system's cached state differs from the actual state of the file system.

`FileError.NOT_FOUND_ERR`  
The specified path could not be found.

`FileError.SECURITY_ERR`  
Security restrictions prohibit obtaining the parent directory's information.

Example
-------

This example renames the file specified by the variable `fileEntry` to `"newname.html"`.

    fileEntry.getParent(function(parent) {
      fileEntry.moveTo(parent, "newname.html", function(updatedEntry) {
        console.log("File " + fileEntry.name + " renamed to newname.html.");
      });
    }, function(error) {
      console.error("An error occurred: Unable to rename " + fileEntry.name
            + " to newname.html.");
    });

This is accomplished by first obtaining a [`FileSystemDirectoryEntry`](../filesystemdirectoryentry) object representing the directory the file is currently located in. Then [`moveTo()`](moveto) is used to rename the file within that directory.

Using promises
--------------

Currently, there isn't a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)-based version of this method. You can, however, create a simple helper function to adapt it, like this:

    function getParentPromise(entry) {
      return new Promise((resolve, reject) => {
        entry.getParent(resolve, reject);
      });
    }

A similar approach can be taken elsewhere in the File and Directory Entries API.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/entries-api/#dom-filesystementry-getparent">File and Directory Entries API<br />
<span class="small">The definition of 'getParent()' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial specification.</td></tr></tbody></table>

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

`getParent`

8

79

No

No

No

11.1

≤37

18

No

No

11.3

1.0

See also
--------

-   [File and Directory Entries API](../file_and_directory_entries_api)
-   [Introduction to the File System API](../file_and_directory_entries_api/introduction)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/FileSystemEntry/getParent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/FileSystemEntry/getParent</a>
