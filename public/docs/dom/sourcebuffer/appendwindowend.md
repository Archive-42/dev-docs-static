SourceBuffer.appendWindowEnd
============================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

**Draft**

This page is not complete.

The `appendWindowEnd` property of the [`SourceBuffer`](../sourcebuffer) interface controls the timestamp for the end of the [append window](https://w3c.github.io/media-source/#append-window), a timestamp range that can be used to filter what media data is appended to the `SourceBuffer`. Coded media frames with timestamps wthin this range will be appended, whereas those outside the range will be filtered out.

The default value of `appendWindowEnd` is positive infinity.

Syntax
------

    var myAppendWindowEnd = sourceBuffer.appendWindowEnd;

    sourceBuffer.appendWindowEnd = 120.0;

### Value

A double, indicating the end time of the append window, in seconds.

### Exceptions

The following exceptions may be thrown when setting a new value for this property.

<table><thead><tr class="header"><th>Exception</th><th>Explanation</th></tr></thead><tbody><tr class="odd"><td><code>InvalidAccessError</code></td><td>An attempt was made to set the value to less than or equal to <a href="appendwindowstart"><code>SourceBuffer.appendWindowStart</code></a>, or <code>NaN</code>.</td></tr><tr class="even"><td><code>InvalidStateError</code></td><td>This <a href="../sourcebuffer"><code>SourceBuffer</code></a> object is being updated (i.e. its <a href="updating"><code>SourceBuffer.updating</code></a> property is currently <code>true</code>), or this <code>SourceBuffer</code> has been removed from the <a href="../mediasource"><code>MediaSource</code></a>.</td></tr></tbody></table>

Example
-------

TBD

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/media-source/#idl-def-sourcebuffer-appendwindowend">Media Source Extensions<br />
<span class="small">The definition of 'appendWindowEnd' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`appendWindowEnd`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SourceBuffer/appendWindowEnd" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SourceBuffer/appendWindowEnd</a>
