SourceBuffer.buffered
=====================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

**Draft**

This page is not complete.

The `buffered` read-only property of the [`SourceBuffer`](../sourcebuffer) interface returns the time ranges that are currently buffered in the `SourceBuffer` as a normalized [`TimeRanges`](../timeranges) object.

Syntax
------

    var myBufferedRange = sourceBuffer.buffered;

### Value

A [`TimeRanges`](../timeranges) object.

Example
-------

TBD

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/media-source/#idl-def-sourcebuffer-buffered">Media Source Extensions<br />
<span class="small">The definition of 'buffered' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`buffered`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SourceBuffer/buffered" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SourceBuffer/buffered</a>
