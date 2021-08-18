# LockedFile.getMetadata()

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

## Summary

The `getMetadata` method allows to retrieve some metadata about the locked file.

## Syntax

    var request = instanceOfLockedFile.getMetadata(param);

### Parameters

`param` <span class="badge inline optional">Optional</span>  
An object used to request specific metadata. Each key is a boolean where `true` means the metadata is expected and where `false` means it is not expected. Note that if the key is `undefined`, it is considered as if it were `true`. The following metadata are supported:

- `size` : will provide the size of the file
- `lastModified` : will provide the date when the file was last modified

### Return

A [`FileRequest`](../filerequest) object. In case of success, the request's `result` is an object with the metadata requested through the param object. They have the following format:

- `size` : a number
- `lastModified` : a `Date` object

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/filesystem-api/">FileSystem API</a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Draft proposal</td></tr></tbody></table>

## See also

- [`LockedFile`](../lockedfile)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/LockedFile/getMetaData" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/LockedFile/getMetaData</a>
