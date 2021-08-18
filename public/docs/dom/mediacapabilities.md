MediaCapabilities
=================

The `MediaCapabilities` interface of the [Media Capabilities API](media_capabilities_api) provides information about the decoding abilities of the device, system and browser. The API can be used to query the browser about the decoding abilities of the device based on codecs, profile, resolution, and bitrates. The information can be used to serve optimal media streams to the user and determine if playback should be smooth and power efficient.

The information is accessed through the `mediaCapabilities` property of the [`Navigator`](navigator) interface.

Methods
-------

[`MediaCapabilities.encodingInfo()`](mediacapabilities/encodinginfo)  
When passed a valid media configuration, it returns a promise with information as to whether the media type is supported, and whether encoding such media would be smooth and power efficient.

[`MediaCapabilities.decodingInfo()`](mediacapabilities/decodinginfo)  
When passed a valid media configuration, it returns a promise with information as to whether the media type is supported, and whether decoding such media would be smooth and power efficient.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/media-capabilities/#mediacapabilities">Media Capabilities<br />
<span class="small">The definition of 'MediaCapabilities' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`MediaCapabilities`

66

79

63

No

55

13

66

66

63

48

13

9.0

`decodingInfo`

66

79

63

No

55

13

66

66

63

48

13

9.0

`encodingInfo`

67

≤79

63

No

?

No

No

67

63

?

No

No

See also
--------

-   [HTMLMediaElement](htmlmediaelement)'s method [canPlayType()](htmlmediaelement/canplaytype)
-   [MediaSource](mediasource)'s method [isTypeSupported()](mediasource/istypesupported)
-   [`Navigator`](navigator) interface

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaCapabilities" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaCapabilities</a>
