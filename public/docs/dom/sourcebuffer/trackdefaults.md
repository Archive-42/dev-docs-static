SourceBuffer.trackDefaults
==========================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `trackDefaults` property of the [`SourceBuffer`](../sourcebuffer) interface specifies the default values to use if kind, label, and/or language information is not available in the [initialization segment](https://w3c.github.io/media-source/#init-segment) of the media to be appended to the `SourceBuffer`.

Syntax
------

    var myTrackDefaults = sourceBuffer.trackDefaults;

    sourceBuffer.trackDefaults = myTrackDefaultList;

### Value

A [`TrackDefaultList`](../trackdefaultlist) object.

### Exceptions

The following exceptions may be thrown when setting a new value for this property.

<table><thead><tr class="header"><th>Exception</th><th>Explanation</th></tr></thead><tbody><tr class="odd"><td><code>InvalidStateError</code></td><td>One or more of the <a href="../sourcebuffer"><code>SourceBuffer</code></a> objects in <a href="../mediasource/sourcebuffers"><code>MediaSource.sourceBuffers</code></a> are being updated (i.e. their <a href="updating"><code>SourceBuffer.updating</code></a> property is currently <code>true</code>), or this <code>SourceBuffer</code> has been removed from the <a href="../mediasource"><code>MediaSource</code></a>.</td></tr></tbody></table>

Example
-------

TBD

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

`trackDefaults`

?

?

No

?

?

?

?

?

No

?

No

?

See also
--------

-   [`MediaSource`](../mediasource)
-   [`SourceBufferList`](../sourcebufferlist)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SourceBuffer/trackDefaults" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SourceBuffer/trackDefaults</a>
