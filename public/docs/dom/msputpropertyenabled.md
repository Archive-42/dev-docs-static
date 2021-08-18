# msPutPropertyEnabled

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

The `msPutPropertyEnabled` method sets whether a given property in the style object is enabled or disabled.

This proprietary method is specific to Internet Explorer and Microsoft Edge.

### Syntax

    var retval = style.msPutPropertyEnabled(propertyName, true);

### Parameters

name\[in\]: Name of the property. (String)

boolean\[in\]: True = Enable the property. False = Disable the property.

### Return value

Type = HRESULT: If this method succeeds, it returns S_OK. Otherwise, it returns an HRESULT error code.

## See also

- [CSS Style Declaration](cssstyledeclaration)
- [Microsoft API extensions](microsoft_extensions)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/msPutPropertyEnabled" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/msPutPropertyEnabled</a>
