SourceBuffer.mode
=================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `mode` property of the [`SourceBuffer`](../sourcebuffer) interface controls whether media segments can be appended to the `SourceBuffer` in any order, or in a strict sequence.

The two available values are:

-   `segments`: The media segment timestamps determine the order in which the segments are played. The segments can be appended to the `SourceBuffer` in any order.
-   `sequence`: The order in which the segments are appended to the `SourceBuffer` determines the order in which they are played. Segment timestamps are generated automatically for the segments that observe this order.

The mode value is initially set when the `SourceBuffer` is created using `MediaSource.addSourceBuffer()`. If timestamps already exist for the media segments, then the value will be set to `segments`; if they don't, then the value will be set to `sequence`.

If you try to set the `mode` property value to `segments` when the initial value is `sequence`, an exception will be thrown. The existing segment order must be maintained in `sequence` mode. You can, however, change the value from `segments` to `sequence`. It just means the play order will be fixed, and new timestamps generated to reflect this.

This property cannot be changed during while the `SourceBuffer` is processing either an [`appendBuffer()`](appendbuffer) or [`remove()`](remove) call.

Syntax
------

    var myMode = sourceBuffer.mode;

    sourceBuffer.mode = 'sequence';

### Value

A [`DOMString`](../domstring).

### Exceptions

The following exceptions may be thrown when setting a new value for this property.

<table><thead><tr class="header"><th>Exception</th><th>Explanation</th></tr></thead><tbody><tr class="odd"><td><code>InvalidAccessError</code></td><td>An attempt was made to set the value to <code>segments</code> when the initial value is <code>sequence</code>.</td></tr><tr class="even"><td><code>InvalidStateError</code></td><td>The <a href="../sourcebuffer"><code>SourceBuffer</code></a> object is being updated (i.e. its <a href="updating"><code>SourceBuffer.updating</code></a> property is currently <code>true</code>), the last media segment appended to this <code>SourceBuffer</code> is incomplete, or this <code>SourceBuffer</code> has been removed from the <a href="../mediasource"><code>MediaSource</code></a>.</td></tr></tbody></table>

Example
-------

This snippet sets the `sourceBuffer` mode to `'sequence'` if it is currently set to `'segments'`, thus setting the play order to the sequence in which media segments are appended.

    var curMode = sourceBuffer.mode;
    if (curMode == 'segments') {
      sourceBuffer.mode = 'sequence';
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/media-source/#idl-def-sourcebuffer-mode">Media Source Extensions<br />
<span class="small">The definition of 'mode' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`mode`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SourceBuffer/mode" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SourceBuffer/mode</a>
