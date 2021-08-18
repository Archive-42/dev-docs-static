SourceBuffer.timestampOffset
============================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

**Draft**

This page is not complete.

The `timestampOffset` property of the [`SourceBuffer`](../sourcebuffer) interface controls the offset applied to timestamps inside media segments that are appended to the `SourceBuffer`.

The initial value of `timestampOffset` is 0.

Syntax
------

    var myOffset = sourceBuffer.timestampOffset;

    sourceBuffer.timestampOffset = 2.5;

### Value

A double, with the offset amount expressed in seconds.

### Exceptions

The following exceptions may be thrown when setting a new value for this property.

<table><thead><tr class="header"><th>Exception</th><th>Explanation</th></tr></thead><tbody><tr class="odd"><td><code>InvalidStateError</code></td><td>One or more of the <a href="../sourcebuffer"><code>SourceBuffer</code></a> objects in <a href="../mediasource/sourcebuffers"><code>MediaSource.sourceBuffers</code></a> are being updated (i.e. their <a href="updating"><code>SourceBuffer.updating</code></a> property is currently <code>true</code>), a media segment inside the <code>SourceBuffer</code> is currently being parsed, or this <code>SourceBuffer</code> has been removed from the <a href="../mediasource"><code>MediaSource</code></a>.</td></tr></tbody></table>

Example
-------

TBD

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/media-source/#idl-def-sourcebuffer-timestampoffset">Media Source Extensions<br />
<span class="small">The definition of 'timestampOffset' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`timestampOffset`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SourceBuffer/timestampOffset" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SourceBuffer/timestampOffset</a>
