TrackDefault
============

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `TrackDefault` interface provides a [`SourceBuffer`](sourcebuffer) with kind, label, and language information for tracks that do not contain this information in the [initialization segments](https://w3c.github.io/media-source/#init-segment) of a media chunk.

A `TrackDefault` object is provided to a `SourceBuffer` object by setting its [`SourceBuffer.trackDefaults`](sourcebuffer/trackdefaults) property.

Constructor
-----------

[`TrackDefault()`](trackdefault/trackdefault)  
Constructs and returns a new `TrackDefault` object.

Properties
----------

 [`TrackDefault.type`](trackdefault/type) <span class="badge inline readonly">Read only </span>   
Returns the type of track that this [`SourceBuffer`](sourcebuffer)'s media segment data relates to (i.e. audio, video, or text track.)

 [`TrackDefault.byteStreamTrackID`](trackdefault/bytestreamtrackid) <span class="badge inline readonly">Read only </span>   
Returns the ID of the specific track that the [`SourceBuffer`](sourcebuffer) should apply to.

 [`TrackDefault.language`](trackdefault/language) <span class="badge inline readonly">Read only </span>   
Returns the default language to use when an [initialization segment](https://w3c.github.io/media-source/#init-segment) does not contain language information for a new track.

 [`TrackDefault.label`](trackdefault/label) <span class="badge inline readonly">Read only </span>   
Returns the default label to use when an [initialization segment](https://w3c.github.io/media-source/#init-segment) does not contain label information for a new track.

 [`TrackDefault.kinds`](trackdefault/kinds) <span class="badge inline readonly">Read only </span>   
Returns the default kinds used when an [initialization segment](https://w3c.github.io/media-source/#init-segment) does not contain kind information for a new track.

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

`TrackDefault`

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

`TrackDefault`

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

`kinds`

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

`label`

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

`language`

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

`type`

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

-   [`MediaSource`](mediasource)
-   [`SourceBuffer`](sourcebuffer)
-   [`TrackDefaultList`](trackdefaultlist)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/TrackDefault" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/TrackDefault</a>
