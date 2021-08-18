FileSystemHandle
================

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `FileSystemHandle` interface of the [`File System Access API`](file_system_access_api) is an object which represents a file or directory entry. Multiple handles can represent the same entry. For the most part you do not work with `FileSystemHandle` directly but rather its child interfaces [`FileSystemFileHandle`](filesystemfilehandle) and [`FileSystemDirectoryHandle`](filesystemdirectoryhandle).

Interfaces based on FileSystemHandle
------------------------------------

Below is a list of interfaces based on the FileSystemHandle interface.

[`FileSystemFileHandle`](filesystemfilehandle)  
Represents a handle to a file entry.

[`FileSystemDirectoryHandle`](filesystemdirectoryhandle)  
Provides a handle to a directory entry.

Properties
----------

 [`kind`](filesystemhandle/kind) <span class="badge inline readonly">Read only </span>   
Returns the type of entry. This is `'file'` if the associated entry is a file or `'directory'`.

 [`name`](filesystemhandle/name) <span class="badge inline readonly">Read only </span>   
Returns the name of the associated entry.

Methods
-------

[`isSameEntry()`](filesystemhandle/issameentry)  
Compares two [`handles`](filesystemhandle) to see if the associated entries (either a file or directory) match.

[`queryPermission()`](filesystemhandle/querypermission)  
Queries the current permission state of the current handle.

[`requestPermission()`](filesystemhandle/requestpermission)  
Requests read or readwrite permissions for the file handle.

Examples
--------

### Checking Type

The below code allows the user to choose a file from the file picker and then tests to see whether the handle returned is a file or directory

    // store a reference to our file handle
    let fileHandle;

    async function getFile() {
      // open file picker
      [fileHandle] = await window.showOpenFilePicker();

      if (fileHandle.kind === 'file') {
        // run file code
      } else if (fileHandle.kind === 'directory')
        // run directory code
      }

    }

### Query/Request Permissions

The following asynchronous function returns true if user has granted read or readwrite permissions to the file handle. Permission is requested if not.

    // fileHandle is a FileSystemFileHandle
    // withWrite is a boolean set to true if write

    async function verifyPermission(fileHandle, withWrite) {
      const opts = {};
      if (withWrite) {
        opts.mode = 'readwrite';
      }

      // Check if we already have permission, if so, return true.
      if (await fileHandle.queryPermission(opts) === 'granted') {
        return true;
      }

      // Request permission to the file, if the user grants permission, return true.
      if (await fileHandle.requestPermission(opts) === 'granted') {
        return true;
      }

      // The user did not grant permission, return false.
      return false;
    }

### Comparing Entries

The following function compares a single entry with an array of entries, and returns a new array with any matching entries removed.

    function removeMatches(fileEntry, entriesArr) {

      let newArr = entriesArr.filter( entry => !fileEntry.isSameEntry(entry) )

      return newArr;
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/file-system-access/#api-filesystemhandle">File System Access API<br />
<span class="small">The definition of 'FileSystemHandle' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`FileSystemHandle`

86

86

No

No

72

No

No

86

No

No

No

14.0

`isSameEntry`

86

86

No

No

72

No

No

86

No

No

No

14.0

`kind`

86

86

No

No

72

No

No

86

No

No

No

14.0

`name`

86

86

No

No

72

No

No

86

No

No

No

14.0

`queryPermission`

86

86

No

No

72

No

No

86

No

No

No

14.0

`requestPermission`

86

86

No

No

72

No

No

86

No

No

No

14.0

See also
--------

-   [File System Access API](file_system_access_api)
-   [The File System Access API: simplifying access to local files](https://web.dev/file-system-access/)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/FileSystemHandle" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/FileSystemHandle</a>
