msCachingEnabled
================

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

The `msCachingEnabled` method gets the current caching state for an [XMLHttpRequest](xmlhttprequest).

This proprietary method is specific to Internet Explorer and Microsoft Edge.

Syntax
------

     var cacheState = XMLHttpRequest.msCachingEnabled();

### Parameters

 *cacheState*\[out, retval\]  
Type = **boolean**. If true, `XMLHttpRequest `is cached to disk. If false, it is not written to disk.

### Return value

Type: **boolean**. If true, `XMLHttpRequest `is cached to disk. If false, it is not written to disk.

See also
--------

-   [msCaching property](mscaching)
-   [Microsoft API extensions](microsoft_extensions)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/msCachingEnabled" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/msCachingEnabled</a>
