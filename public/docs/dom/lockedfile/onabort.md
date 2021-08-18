LockedFile.onabort
==================

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

Summary
-------

Specifies an event listener to receive `abort` events. These events occur when the locked file has been aborted with the [`LockedFile.abort()`](abort) method.

Syntax
------

    instanceOfLockedFile.onabort = funcRef;

Where `funcRef` is a function to be called when the `abort` event occurs.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/filesystem-api/">FileSystem API</a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Draft proposal.</td></tr></tbody></table>

See also
--------

-   [`LockedFile`](../lockedfile)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/LockedFile/onabort" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/LockedFile/onabort</a>
