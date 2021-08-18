Navigator.msSaveOrOpenBlob
==========================

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `Navigator.msSaveOrOpenBlob()` method saves the [`File`](../file) or [`Blob`](../blob) to disk. This method behaves in the same way as [`Navigator.msSaveBlob()`](mssaveblob) except that this enables the file open option.

Syntax
------

    navigator.msSaveOrOpenBlob(blob, defaultName);

### Parameters

`blob`  
A blob to be saved.

`defaultName`  
The file name to be used when saving file.

### Return value

True is returned as long as the download notification bar is displayed, or false if a failure occurred.

Notes
-----

When a site calls this method, the behavior is the same as when Windows Internet Explorer downloads a file with the following in the header:

    Content-Length: <blob.size>
    Content-Type: <blob.type>
    Content-Disposition: attachment;filename=<defaultName>

Specifications
--------------

Not part of any specifications.

Browser compatibility
---------------------

No compatibility data found for `api.Navigator.msSaveOrOpenBlob`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Navigator/msSaveOrOpenBlob" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Navigator/msSaveOrOpenBlob</a>
