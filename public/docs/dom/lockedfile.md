LockedFile
==========

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

Summary
-------

The `LockedFile` interface provides tools to deal with a given file with all the necessary locks.

Properties
----------

 [`LockedFile.fileHandle`](lockedfile/filehandle) <span class="badge inline readonly">Read only </span>   
The [`IDBMutableFile`](idbmutablefile) object from which the lock was opened.

 [`LockedFile.mode`](lockedfile/mode) <span class="badge inline readonly">Read only </span>   
The mode for accessing the file; can be `readonly` or `readwrite`.

 [`LockedFile.active`](lockedfile/active) <span class="badge inline readonly">Read only </span>   
A flag indicating if the file can be accessed (`true`) or not (`false`).

[`LockedFile.location`](lockedfile/location)  
The position of the reading/writing pointer within the file.

### Events Handler

[`LockedFile.oncomplete`](lockedfile/oncomplete)  
The `complete` event is triggered each time a read or write operation is successful.

[`LockedFile.onabort`](lockedfile/onabort)  
The `abort` event is triggered each time the [`abort()`](lockedfile/abort) method is called.

[`LockedFile.onerror`](lockedfile/onerror)  
The `error` event is triggered each time something goes wrong.

Methods
-------

[`LockedFile.getMetadata()`](lockedfile/getmetadata)  
Allows to retrieve the file metadata (size and date of the last modification). Returns a [`FileRequest`](filerequest).

[`LockedFile.readAsArrayBuffer()`](lockedfile/readasarraybuffer)  
Allows to retrieve a part of the content of the file as an [`ArrayBuffer`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer). Returns a [`FileRequest`](filerequest) object.

[`LockedFile.readAsText()`](lockedfile/readastext)  
Allows to retrieve a part of the content of the file as a string. Returns a [`FileRequest`](filerequest) object.

[`LockedFile.write()`](lockedfile/write)  
Allows to write some data in the file starting at the [`location`](lockedfile/location) offset. Returns a [`FileRequest`](filerequest) object.

[`LockedFile.append()`](lockedfile/append)  
Allows to write some data at the end of the file. Returns a [`FileRequest`](filerequest) object.

[`LockedFile.truncate()`](lockedfile/truncate)  
Allows to truncate the file's content. Returns a [`FileRequest`](filerequest) object.

[`LockedFile.flush()`](lockedfile/flush)  
Allows to guarantee that any buffered data has been transferred to disk.

[`LockedFile.abort()`](lockedfile/abort)  
Makes the `LockedFile` inactive and cancels all ongoing operations.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/filesystem-api/">FileSystem API</a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Draft proposal.</td></tr></tbody></table>

See also
--------

-   [`IDBMutableFile`](idbmutablefile)
-   [`FileRequest`](filerequest)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/LockedFile" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/LockedFile</a>
