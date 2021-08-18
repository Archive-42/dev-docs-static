SourceBuffer.appendBuffer()
===========================

**Draft**

This page is not complete.

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `appendBuffer()` method of the [`SourceBuffer`](../sourcebuffer) interface appends media segment data from an [`ArrayBuffer`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer) or `ArrayBufferView` object to the `SourceBuffer`.

Syntax
------

    sourceBuffer.appendBuffer(source);

### Parameters

`source`  
A [`BufferSource`](../buffersource) (that is, either an [`ArrayBufferView`](../arraybufferview) or [`ArrayBuffer`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer)) which contains the media segment data you want to add to the `SourceBuffer`.

### Return value

[`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined).

### Exceptions

None.

Example
-------

TBD.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/media-source/#dom-sourcebuffer-appendbuffer">Media Source Extensions<br />
<span class="small">The definition of 'appendBuffer()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`appendBuffer`

23

12

42

11

Only works on Windows 8+.

15

8

4.4.3

33

No

14

No

3.0

See also
--------

-   [`MediaSource`](../mediasource)
-   [`SourceBufferList`](../sourcebufferlist)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SourceBuffer/appendBuffer" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SourceBuffer/appendBuffer</a>
