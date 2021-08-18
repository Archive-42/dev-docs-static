LockedFile.active
=================

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

The `active` property allows to know if the [`LockedFile`](../lockedfile) object is still usable (`true`) or not (`false`). If the object is inactive then it is impossible to perform any read or write operation with it. Typically, a [`LockedFile`](../lockedfile) object becomes inactive when the [`LockedFile.abort()`](abort) method is called or if an error occurs.

Syntax
------

    var state = instanceOfLockedFile.active

### Value

A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean).

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/filesystem-api/">FileSystem API</a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Draft Proposal.</td></tr></tbody></table>

See also
--------

-   [`LockedFile`](../lockedfile)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/LockedFile/active" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/LockedFile/active</a>
