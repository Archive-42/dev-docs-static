MediaCapabilitiesInfo
=====================

The `MediaCapabilitiesInfo` interface of the [Media Capabilities API](media_capabilities_api) is made available when the promise returned by the [`MediaCapabilities.encodingInfo()`](mediacapabilities/encodinginfo) or [`MediaCapabilities.decodingInfo()`](mediacapabilities/decodinginfo) methods of the [`MediaCapabilities`](mediacapabilities) interface fulfills, providing information as to whether the media type is supported, and whether encoding or decoding such media would be smooth and power efficient.

Properties
----------

The `MediaCapabilitiesInfo` interface contains three Boolean attribues:

-   `supported`: Given the properties defined in the [`MediaConfiguration`](mediaconfiguration), can the specified piece of media content be encoded (if [`MediaEncodingConfiguration`](mediaencodingconfiguration) is set) or decode (if [`MediaDecodingConfiguration`](mediadecodingconfiguration) is set) at all? If yes, `supported` is *true*. Otherwise, it is *false*.
-   `smooth`: Given the properties defined in the [`MediaConfiguration`](mediaconfiguration), will the playback of the specified piece of media be high quality? Will it be smooth? If `supported` is `true`, and playback will be smooth, `smooth` is *true*, Otherwise, is it *false.*
-   `powerEfficient`: Given the properties defined in the [`MediaConfiguration`](mediaconfiguration), will the playback of the specified piece of media be power efficient? If `supported` is `true`, and playback will be power efficient, `powerEfficient` is *true*, Otherwise, is it *false.*

Browsers will report a supported media configuration as `smooth` and `powerEfficient` until stats on this device have been recorded. All supported audio codecs are reported to be power efficient.

Example
-------

    // MediaConfiguration to be tested
    const mediaConfig = {
        type : 'file',
        audio : {
            contentType : "audio/ogg",
            channels : 2,
            bitrate : 132700,
            samplerate : 5200
         },
    };

    // check support and performance
    navigator.mediaCapabilities.decodingInfo(mediaConfig).then(result => { // result contains the media capabilities information
        console.log('This configuration is ' +
            (result.supported ? '' : 'not ') + 'supported, ' +             // Can the media, as configured, be decoded by the user agent
            (result.smooth ? '' : 'not ') + 'smooth, and ' +               // is it smooth?
            (result.powerEfficient ? '' : 'not ') + 'power efficient.')    // is it power efficient?
    });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/media-capabilities/#media-capabilities-info">Media Capabilities<br />
<span class="small">The definition of 'MediaCapabilitiesInfo' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`MediaCapabilitiesInfo`

66

≤79

63

No

?

?

66

66

63

?

?

9.0

`powerEfficient`

66

≤79

63

No

?

?

66

66

63

?

?

9.0

`smooth`

66

≤79

63

No

?

?

66

66

63

?

?

9.0

`supported`

66

≤79

63

No

?

?

66

66

63

?

?

9.0

See also
--------

-   [`MediaConfiguration`](mediaconfiguration)
-   [`MediaCapabilities.encodingInfo()`](mediacapabilities/encodinginfo)
-   [`MediaCapabilities.decodingInfo()`](mediacapabilities/decodinginfo)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaCapabilitiesInfo" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaCapabilitiesInfo</a>
