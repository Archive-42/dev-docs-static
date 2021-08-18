TrackDefault.byteStreamTrackID
==============================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `byteStreamTrackID` read-only property of the [`TrackDefault`](../trackdefault) interface returns the ID of the specific track that the [`SourceBuffer`](../sourcebuffer) should apply to.

If not specified in the constructor, this value will be an empty string and the `SourceBuffer` can contain any tracks of the specified [`TrackDefault.type`](type).

Syntax
------

    var myID = TrackDefault.byteStreamTrackID;

### Value

A [`DOMString`](../domstring).

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

`byteStreamTrackID`

No

≤18

No

No

No

No

No

No

No

No

No

No

See also
--------

-   [`MediaSource`](../mediasource)
-   [`SourceBuffer`](../sourcebuffer)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/TrackDefault/byteStreamTrackID" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/TrackDefault/byteStreamTrackID</a>
