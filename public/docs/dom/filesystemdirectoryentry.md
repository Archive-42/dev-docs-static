# FileSystemDirectoryEntry

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `FileSystemDirectoryEntry` interface of the [File and Directory Entries API](file_and_directory_entries_api) represents a directory in a file system. It provides methods which make it possible to access and manipulate the files in a directory, as well as to access the entries within the directory.

## Basic concepts

You can create a new directory by calling [`getDirectory()`](filesystemdirectoryentry/getdirectory). If you want to create subdirectories, create each child directory in sequence. If you try creating a directory using a full path that includes parent directories that do not exist yet, an error is returned. So create the hierarchy by recursively adding a new path after creating the parent directory.

### Example

In the following code snippet, we create a directory called "Documents."

    // Taking care of the browser-specific prefixes.
    window.requestFileSystem = window.requestFileSystem || window.webkitRequestFileSystem;
    window.directoryEntry = window.directoryEntry || window.webkitDirectoryEntry;

    ...

    function onFs(fs){
      fs.root.getDirectory('Documents', {create:true}, function(directoryEntry){
        //directoryEntry.isFile === false
        //directoryEntry.isDirectory === true
        //directoryEntry.name === 'Documents'
        //directoryEntry.fullPath === '/Documents'

        }, onError);

      }

    // Opening a file system with temporary storage
    window.requestFileSystem(TEMPORARY, 1024*1024 /*1MB*/, onFs, onError);

## Properties

_This interface has no properties of its own, but inherits properties from its parent interface, [`FileSystemEntry`](filesystementry)._

## Methods

_This interface inherits methods from its parent interface, [`FileSystemEntry`](filesystementry)._

[`createReader()`](filesystemdirectoryentry/createreader)  
Creates a [`FileSystemDirectoryReader`](filesystemdirectoryreader) object which can be used to read the entries in this directory.

[`getDirectory()`](filesystemdirectoryentry/getdirectory)  
Returns a [`FileSystemDirectoryEntry`](filesystemdirectoryentry) object representing a directory located at a given path, relative to the directory on which the method is called.

[`getFile()`](filesystemdirectoryentry/getfile)  
Returns a [`FileSystemFileEntry`](filesystemfileentry) object representing a file located within the directory's hierarchy, given a path relative to the directory on which the method is called.

### Obsolete methods

[`removeRecursively()`](filesystemdirectoryentry/removerecursively)  
Deletes a directory and all of its contents, including the contents of subdirectories. This has been removed from the spec.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/entries-api/#api-directoryentry">File and Directory Entries API<br />
<span class="small">The definition of 'FileSystemDirectoryEntry' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td></td></tr></tbody></table>

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

`FileSystemDirectoryEntry`

8

79

50

No

Yes

11.1

≤37

18

50

No

11.3

1.0

`createReader`

13

79

50

No

No

11.1

≤37

18

50

No

11.3

1.0

`getDirectory`

8

79

50

In Firefox, the `errorCallback`'s input parameter is a `DOMException` rather than a `FileError` object.

No

No

11.1

≤37

18

50

In Firefox, the `errorCallback`'s input parameter is a `DOMException` rather than a `FileError` object.

No

11.3

1.0

`getFile`

8

79

50

In Firefox, the `errorCallback`'s input parameter is a `DOMException` rather than a `FileError` object.

No

No

11.1

≤37

18

50

In Firefox, the `errorCallback`'s input parameter is a `DOMException` rather than a `FileError` object.

No

11.3

1.0

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

- [File and Directory Entries API](file_and_directory_entries_api)
- [Introduction to the File System API](file_and_directory_entries_api/introduction)
- [`FileSystemDirectoryReader`](filesystemdirectoryreader)
- [`FileSystemEntry`](filesystementry)
- [`FileSystemFileEntry`](filesystemfileentry)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/FileSystemDirectoryEntry" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/FileSystemDirectoryEntry</a>
