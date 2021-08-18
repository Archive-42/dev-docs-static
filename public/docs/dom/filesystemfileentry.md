FileSystemFileEntry
===================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `FileSystemFileEntry` interface of the [File System API](file_and_directory_entries_api/introduction) represents a file in a file system. It offers properties describing the file's attributes, as well as the [`file()`](filesystemfileentry/file) method, which creates a [`File`](file) object that can be used to read the file.

Properties
----------

*Inherits the properties of its parent interface, [`FileSystemEntry`](filesystementry), but has no properties unique to this interface.*

Methods
-------

[`file()`](filesystemfileentry/file)  
Creates a new [`File`](file) object which can be used to read the file.

### Obsolete methods

 [`createWriter()`](filesystemfileentry/createwriter) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
Creates a new <span class="page-not-created">`FileWriter`</span> object which allows writing to the file represented by the file system entry.

Basic concepts
--------------

To write content to file, create a <span class="page-not-created">`FileWriter`</span> object by calling [`createWriter()`](filesystemfileentry/createwriter). To read a file, obtain a [`File`](file) object representing its contents by calling [`file()`](filesystemfileentry/file).

### Example

The following code creates an empty file called "`log.txt"` (if it doesn't exist) and fills it with the text "Meow". Inside the success callback, event handlers are set up to handle the `error` `error` and `writeend` events. The text data is written to the file by creating a blob, appending text to it, and passing the blob to <span class="page-not-created">`FileWriter.write()`</span>.

    function onInitFs(fs) {
      fs.root.getFile('log.txt', {create: true}, function(fileEntry) {

        // Create a FileWriter object for our FileSystemFileEntry (log.txt).
        fileEntry.createWriter(function(fileWriter) {
          fileWriter.onwriteend = function(e) {
            console.log('Write completed.');
          };

          fileWriter.onerror = function(e) {
            console.log('Write failed: ' + e.toString());
          };

          // Create a new Blob and write it to log.txt.
          var bb = new BlobBuilder();
          bb.append('Meow');

          fileWriter.write(bb.getBlob('text/plain'));
        }, errorHandler);

      }, errorHandler);

    }

    window.requestFileSystem(window.TEMPORARY, 1024*1024, onInitFs, errorHandler);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/entries-api/#api-fileentry">File and Directory Entries API<br />
<span class="small">The definition of 'FileSystemFileEntry' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Draft of proposed API</td></tr></tbody></table>

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

`FileSystemFileEntry`

8

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

`file`

8

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

See also
--------

-   [File and Directory Entries API](file_and_directory_entries_api)
-   [Introduction to the File System API](file_and_directory_entries_api/introduction)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/FileSystemFileEntry" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/FileSystemFileEntry</a>
