SourceBuffer.appendBufferAsync()
================================

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `appendBufferAsync()` method of the [`SourceBuffer`](../sourcebuffer) interface begins the process of asynchronously appending media segment data from an [`ArrayBuffer`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer) or [`ArrayBufferView`](../arraybufferview) object to the `SourceBuffer`. It returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) which is fulfilled once the buffer has been appended.

Syntax
------

    appendPromise = sourceBuffer.appendBufferAsync(source);

### Parameters

`source`  
A [`BufferSource`](../buffersource) (that is, either an [`ArrayBufferView`](../arraybufferview) or [`ArrayBuffer`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer)) which contains the media segment data you want to add to the `SourceBuffer`.

### Return value

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) which is fulfilled when the buffer has been added successfully to the `SourceBuffer`, or `null` if the request could not be initiated.

Example
-------

This simplified example async function, `fillSourceBuffer()`, takes as input parameters [`BufferSource`](../buffersource), `buffer`, and a `SourceBuffer` to which to append the source media from the buffer.

    async function fillSourceBuffer(buffer, msBuffer) {
      try {
        while(true) {
          await msBuffer.appendBufferAsync(buffer);
        }
      } catch(e) {
        handleException(e);
      }
    }

Specifications
--------------

Not currently part of any specification. This is being experimented with under the auspices of the **Web Platform Incubator Community Group** (WICG).

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/media-source/">Media Source Extensions</a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition; does not include this method.</td></tr></tbody></table>

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

`appendBufferAsync`

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
-   [`SourceBuffer.appendBuffer()`](appendbuffer)
-   [`MediaSource`](../mediasource)
-   [`SourceBufferList`](../sourcebufferlist)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SourceBuffer/appendBufferAsync" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SourceBuffer/appendBufferAsync</a>
