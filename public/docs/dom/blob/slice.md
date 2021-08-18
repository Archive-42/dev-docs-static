# Blob.slice()

The [`Blob`](../blob) interface's `slice()` method creates and returns a new `Blob` object which contains data from a subset of the blob on which it's called.

## Syntax

    var newBlob = blob.slice(start, end, contentType);

### Parameters

`start` <span class="badge inline optional">Optional</span>  
An index into the [`Blob`](../blob) indicating the first byte to include in the new [`Blob`](../blob). If you specify a negative value, it's treated as an offset from the end of the [`Blob`](../blob) toward the beginning. For example, -10 would be the 10th from last byte in the [`Blob`](../blob). The default value is 0. If you specify a value for `start` that is larger than the size of the source [`Blob`](../blob), the returned [`Blob`](../blob) has size 0 and contains no data.

`end` <span class="badge inline optional">Optional</span>  
An index into the [`Blob`](../blob) indicating the first byte that will \*not\* be included in the new [`Blob`](../blob) (i.e. the byte exactly at this index is not included). If you specify a negative value, it's treated as an offset from the end of the [`Blob`](../blob) toward the beginning. For example, -10 would be the 10th from last byte in the [`Blob`](../blob). The default value is `size`.

`contentType` <span class="badge inline optional">Optional</span>  
The content type to assign to the new [`Blob`](../blob); this will be the value of its `type` property. The default value is an empty string.

### Return value

A new [`Blob`](../blob) object containing the specified subset of the data contained within the blob on which this method was called. The original blob is not altered.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/FileAPI/#dfn-slice">File API<br />
<span class="small">The definition of 'Blob.slice()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

## Browser compatibility

Desktop

Mobile

Chrome

Edge

Firefox

Internet Explorer

Opera

Safari

WebView Android

Chrome Android

Firefox for Android

Opera Android

Safari on IOS

Samsung Internet

`slice`

21

5-25

12

13

Prior to Firefox 12, there was a bug that affected the behavior of `Blob.slice()`; it did not work for `start` and `end` positions outside the range of signed 64-bit values; it has now been fixed to support unsigned 64-bit values.

5-13

10

12

5.1

≤37

25

18-25

14

Yes

Yes

1.5

1.0-1.5

The compatibility table on this page is generated from structured data. If you'd like to contribute to the data, please check out <https://github.com/mdn/browser-compat-data> and send us a pull request.

## See also

- [`Blob`](../blob)
- [Using files from web applications](../file/using_files_from_web_applications)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Blob/slice" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Blob/slice</a>
