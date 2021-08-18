SourceBuffer.removeAsync()
==========================

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `removeAsync()` method of the [`SourceBuffer`](../sourcebuffer) interface starts the process of asynchronously removing from the `SourceBuffer` media segments found within a specific time range. A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) is returned, which is fulfilled when the buffers in the specified time range have been removed.

This method can only be called when [`updating`](updating) is `false`. If that's not the case, call [`abort()`](abort) instead.

Syntax
------

    removePromise = sourceBuffer.removeAsync(start, end);

### Parameters

`start`  
A double representing the start of the time range, in seconds.

`end`  
A double representing the end of the time range, in seconds.

### Return value

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) whose fulfillment handler is executed once the buffers in the specified time range have been removed from the `SourceBuffer`.

Example
-------

This example establishes an asynchronous function, `emptySourceBuffer()`, which clears the contents of the specified `SourceBuffer`.

    async function emptySourceBuffer(msBuffer) {
      await msBuffer.removeAsync(0, Infinity).catch(function(e) {
        handleException(e);
      }
    }

Specifications
--------------

Not currently part of the MSE specification.

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/media-source/">Media Source Extensions</a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

Browser compatibility
---------------------

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

`removeAsync`

No

No

62

No

No

No

No

Yes

No

No

No

Yes

See also
--------

-   [Media Source Extensions API](../media_source_extensions_api)
-   [`SourceBuffer.remove()`](remove)
-   [`MediaSource`](../mediasource)
-   [`SourceBufferList`](../sourcebufferlist)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SourceBuffer/removeAsync" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SourceBuffer/removeAsync</a>
