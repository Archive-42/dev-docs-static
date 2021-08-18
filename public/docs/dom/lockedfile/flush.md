LockedFile.flush()
==================

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

Summary
-------

The `flush` method is used to ensure any change made to a file is properly written on disk.

For performance reasons, a [`LockedFile`](../lockedfile) object buffers all its operation in memory. This allows fast writing and reading operations. Periodically, the data are written onto disk. However, if something goes wrong before that, some operations can be lost. To avoid that, it's possible to force a write onto the disk by calling the `flush` method.

Syntax
------

    var request = instanceOfLockedFile.flush();

### Return

A [`FileRequest`](../filerequest) object to handle the success or failure of the operation.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/filesystem-api/">FileSystem API</a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Draft proposal</td></tr></tbody></table>

See also
--------

-   [`LockedFile`](../lockedfile)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/LockedFile/flush" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/LockedFile/flush</a>
