IDBMutableFile
==============

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

Summary
-------

The `IDBMutableFile` interface provides access in read or write mode to a file, dealing with all the necessary locks.

**Note**: This interface used to be called `FileHandle` , but it was changed to this ([bug 1006485](https://bugzilla.mozilla.org/show_bug.cgi?id=1006485).)

As `IDBMutableFile` objects are bound to a fake file system built on top of IndexedDB, such an object is created using the <span class="page-not-created">`IDBDatabase.createMutableFile`</span> method.

Properties
----------

 <span class="page-not-created">`MutableFile.name`</span> <span class="badge inline readonly">Read only </span>   
The name of the handled file.

 <span class="page-not-created">`MutableFile.type`</span> <span class="badge inline readonly">Read only </span>   
The MIME type of the handled file.

### Events Handler

<span class="page-not-created">`MutableFile.onabort`</span>  
The `abort` event is triggered each time the handled file is aborted.

<span class="page-not-created">`MutableFile.onerror`</span>  
The `error` event is triggered each time something goes wrong.

Methods
-------

<span class="page-not-created">`MutableFile.open()`</span>  
Returns a [`LockedFile`](lockedfile) object to read or write the associated file safely.

<span class="page-not-created">`MutableFile.getFile()`</span>  
Returns a <span class="page-not-created">`DOMRequest`</span> object. In case of success, the request's result is a [`File`](file) object representing a snapshot of the handled file.

Specifications
--------------

Not part of any specification at present.

See also
--------

-   [`LockedFile`](lockedfile)
-   [`File`](file)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/IDBMutableFile" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/IDBMutableFile</a>
