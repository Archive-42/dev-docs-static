# LockedFile.truncate()

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

## Summary

The `truncate` method is used to remove some data within the file.

If the method is called with no argument, the operation removes all the bytes starting at the index set in [`LockedFile.location`](location).

If the method is called with an argument, the operation removes all the bytes starting at the index corresponding to the parameter and regardless of the value of [`LockedFile.location`](location).

## Syntax

    var request = instanceOfLockedFile.truncate(start);

### Parameters

`start` <span class="badge inline optional">Optional</span>  
A number representing the index where to start the operation.

### Return

A [`FileRequest`](../filerequest) object to handle the success or failure of the operation.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/filesystem-api/">FileSystem API</a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Draft proposal</td></tr></tbody></table>

## See also

- [`LockedFile`](../lockedfile)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/LockedFile/truncate" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/LockedFile/truncate</a>
