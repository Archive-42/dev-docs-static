# msGetRegionContent

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

The `msGetRegionContent` returns an array of Range instances corresponding to the content from the region flow that is positioned in the region.

This proprietary method is specific to Internet Explorer browser.

### Syntax

    var retVal = element.msGetRegionContent();

### Parameters

**retVal** \[out, reval\]

Type: _MSRangeCollection_

The name of the property to enable.

### Return value

Type: _Boolean_

Returned ranges are sorted by document position and do not overlap. If an element is not a region, this method throws a `DOMException` with the `InvalidAccessError` error code. This is only available to regions that are document elements and not to regions that are pseudo-elements.

## See also

- [Microsoft API extensions](microsoft_extensions)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/msGetRegionContent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/msGetRegionContent</a>
