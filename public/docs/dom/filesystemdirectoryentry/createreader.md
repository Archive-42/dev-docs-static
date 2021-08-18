# FileSystemDirectoryEntry.createReader()

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The [`FileSystemDirectoryEntry`](../filesystemdirectoryentry) interface's method ` createReader``() ` returns a [`FileSystemDirectoryReader`](../filesystemdirectoryreader) object which can be used to read the entries in the directory.

## Syntax

    directoryReader = FileSystemDirectoryEntry.createReader();

### Parameters

None.

### Return value

A [`FileSystemDirectoryReader`](../filesystemdirectoryreader) object which can be used to read the directory's entries.

## Example

This example creates a method called `readDirectory()`, which fetches all of the entries in the specified [`FileSystemDirectoryEntry`](../filesystemdirectoryentry) and returns them in an array.

    function readDirectory(directory) {
      let dirReader = directory.createReader();
      let entries = [];

      let getEntries = function() {
        dirReader.readEntries(function(results) {
          if (results.length) {
            entries = entries.concat(toArray(results));
            getEntries();
          }
        }, function(error) {
          /* handle error -- error is a FileError object */
        });
      };

      getEntries();
      return entries;
    }

This works by creating an internal function, `getEntries()`, which calls itself recursively to get all the entries in the directory, concatenating each batch to the array. Each iteration, [`readEntries()`](../filesystemdirectoryreader/readentries) is called to get more entries. When it returns an empty array, the end of the directory has been reached, and the recursion ends. Once control is returned to `readDirectory()`, the array is returned to the caller.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/entries-api/#dom-filesystemdirectoryentry-createreader">File and Directory Entries API<br />
<span class="small">The definition of 'createReader()' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial specification.</td></tr></tbody></table>

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

## See also

- [File and Directory Entries API](../file_and_directory_entries_api)
- [Introduction to the File System API](../file_and_directory_entries_api/introduction)
- [`FileSystemDirectoryReader`](../filesystemdirectoryreader)
- [`FileSystemDirectoryEntry`](../filesystemdirectoryentry)
- [`FileSystemFileEntry`](../filesystemfileentry)
- [`FileSystemEntry`](../filesystementry)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/FileSystemDirectoryEntry/createReader" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/FileSystemDirectoryEntry/createReader</a>
