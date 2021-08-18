# LockedFile.write()

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

## Summary

The `write` method is used to write some data within the file.

The write starts at the position set in [`LockedFile.location`](location) and moves that position by the number of written bytes.

## Syntax

    var request = instanceOfLockedFile.write(data);

### Parameters

`data`  
The data to write into the file. It can be a string or an [`ArrayBuffer`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer).

### Return

A [`FileRequest`](../filerequest) object to handle the success or failure of the operation.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/filesystem-api/">FileSystem API</a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Draft proposal</td></tr></tbody></table>

## See also

- [`LockedFile`](../lockedfile)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/LockedFile/write" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/LockedFile/write</a>
