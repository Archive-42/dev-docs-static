# FileHandle.open()

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

## Summary

The `open` method returns a [`LockedFile`](../lockedfile) object that allows to safely write in the file.

## Syntax

    var myFile = instanceOfFileHandle.open(mode);

### Parameters

mode  
A string that specifies the writing mode for the file. It can be `readonly` or `readwrite`.

### Return

A [`LockedFile`](../lockedfile) object.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/filesystem-api/">FileSystem API</a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Draft proposal</td></tr></tbody></table>

## See also

- [`IDBMutableFile`](../idbmutablefile)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/IDBMutableFile/open" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/IDBMutableFile/open</a>
