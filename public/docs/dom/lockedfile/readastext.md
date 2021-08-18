# LockedFile.readAsText()

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

## Summary

The `readAsText` method is used to read the content of the [`LockedFile`](../lockedfile) object and provide the result of that reading as a string. In many ways, it performs like the [`FileReader.readAsText()`](../filereader/readastext) method.

The reading operation starts at the position given by the [`LockedFile.location`](location) property.

## Syntax

    var request = instanceOfLockedFile.readAsText(size[, encoding]);

### Parameters

`size`  
A number representing the number of bytes to read in the file.

`encoding` <span class="badge inline optional">Optional</span>  
A string indicating the encoding to use for the returned data. By default, UTF-8 is assumed if this parameter is not specified.

### Return

A [`FileRequest`](../filerequest) object to handle the success or failure of the operation. In case of success, the request's `result` is a string representing the data that have been read.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/filesystem-api/">FileSystem API</a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Draft proposal</td></tr></tbody></table>

## See also

- [`LockedFile`](../lockedfile)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/LockedFile/readAsText" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/LockedFile/readAsText</a>
