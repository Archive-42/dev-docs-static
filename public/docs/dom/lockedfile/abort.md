# LockedFile.abort()

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

## Summary

The `abort` method is used to release the lock on the [`LockedFile`](../lockedfile) object, making it inactive: its [`active`](active) property is set to false and all ongoing operations are canceled.

**Note:** When an ongoing operation is canceled, there is no rollback (it is not a database transaction), therefore the file can be corrupted if the canceled operation was performing some writing.

## Syntax

    var request = instanceOfLockedFile.abort();

### Return

A [`FileRequest`](../filerequest) object to handle the success or failure of the operation.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/filesystem-api/">FileSystem API</a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Draft proposal</td></tr></tbody></table>

## See also

- [`LockedFile`](../lockedfile)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/LockedFile/abort" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/LockedFile/abort</a>
