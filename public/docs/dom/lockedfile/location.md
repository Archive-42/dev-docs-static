LockedFile.location
===================

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

Summary
-------

The `location` property is a zero-based index representing the position of the read/write pointer within the file. Its value indicates at which bytes within the file any write or read operation will start.

This value is changed automatically after every read and write operation. The special value `null` means end-of-file.

This property can be changed at will.

Syntax
------

    var location = instanceOfLockedFile.location

Value
-----

A number.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/filesystem-api/">FileSystem API</a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Draft Proposal.</td></tr></tbody></table>

See also
--------

-   [`LockedFile`](../lockedfile)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/LockedFile/location" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/LockedFile/location</a>
