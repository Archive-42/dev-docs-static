# FileRequest

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

## Summary

The `FileRequest` interface extends the <span class="page-not-created">`DOMRequest`</span> interface to provide some extra properties necessary for the [`LockedFile`](lockedfile) objects.

## Properties

[`FileRequest.lockedFile`](filerequest/lockedfile) <span class="badge inline readonly">Read only </span>  
The [`LockedFile`](lockedfile) object from which the request was started.

[`FileRequest.onprogress`](filerequest/onprogress)  
A callback handler called repeatedly while the operation represented by the `FileRequest` is in progress.

The `FileRequest` interface also inherits from the <span class="page-not-created">`DOMRequest`</span> interface.

{{page("/en-US/docs/Web/API/DOMRequest","Properties")}}

## Methods

None.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/filesystem-api/">FileSystem API</a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Draft proposal.</td></tr></tbody></table>

## See also

- [`IDBMutableFile`](idbmutablefile)
- [`LockedFile`](lockedfile)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/FileRequest" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/FileRequest</a>
