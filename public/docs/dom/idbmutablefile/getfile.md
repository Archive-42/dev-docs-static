FileHandle.getFile()
====================

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

Summary
-------

The `getFile` method allows to retrieve a read-only snapshot of the handled file in the form of a [`File`](../file) object.

Syntax
------

    var request = instanceOfFileHandle.getFile();

### Return

A <span class="page-not-created">`DOMRequest`</span> object. In case of success, the request's `result` is a [`File`](../file) object.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/filesystem-api/">FileSystem API</a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Draft proposal</td></tr></tbody></table>

See also
--------

-   [`IDBMutableFile`](../idbmutablefile)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/IDBMutableFile/getFile" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/IDBMutableFile/getFile</a>
