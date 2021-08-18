MediaCapabilities.encodingInfo()
================================

The `MediaCapabilities.encodingInfo()` method, part of the [`MediaCapabilities`](../mediacapabilities) interface of the [Media Capabilities API](../mediacapabilities), returns a promise with the tested media configuration's [`MediaCapabilitiesInfo`](../mediacapabilitiesinfo); this contains the three Boolean properties `supported`, `smooth`, and `powerefficient`, which describe how compatible the device is with the type of media.

Syntax
------

    mediaCapabilities.encodingInfo(mediaEncodingConfiguration)

### Parameters

[`mediaEncodingConfiguration`](../mediaencodingconfiguration)  
A valid [`MediaEncodingConfiguration`](../mediaencodingconfiguration) dictionary containing a valid media encoding type of `record` or `transmission` and a valid media configuration: either an [`AudioConfiguration`](../audioconfiguration) or [`VideoConfiguration`](../videoconfiguration) dictionary.

### Return value

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) fulfilling with a [`MediaCapabilitiesInfo`](../mediacapabilitiesinfo) interface containing three Boolean attributes:

-   `supported`
-   `smooth`
-   `powerEfficient`

### Exceptions

A `TypeError` is raised if the `MediaConfiguration` passed to the `encodingInfo()` method is invalid, either because the type is not video or audio, the `contentType` is not a valid codec MIME type, or any other error in the media configuration passed to the method, including omitting any of the [media encoding configuration](../mediaencodingconfiguration) elements.

Example
-------

    //Create media configuration to be tested
    const mediaConfig = {
        type : 'record', // or 'transmission'
        video : {
            contentType : "video/webm;codecs=vp8.0", // valid content type
            width : 1920,     // width of the video
            height : 1080,    // height of the video
            bitrate : 120000, // number of bits used to encode 1s of video
            framerate : 48   // number of frames making up that 1s.
         }
    };

    // check support and performance
    navigator.mediaCapabilities.encodingInfo(mediaConfig).then(result => {
        console.log('This configuration is ' +
            (result.supported ? '' : 'not ') + 'supported, ' +
            (result.smooth ? '' : 'not ') + 'smooth, and ' +
            (result.powerEfficient ? '' : 'not ') + 'power efficient.')
    });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/media-capabilities/#dom-mediacapabilities-encodinginfo-configuration-configuration">Media Capabilities<br />
<span class="small">The definition of 'encodingInfo()' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

-   [`MediaEncodingConfiguration`](../mediaencodingconfiguration)
-   [`VideoConfiguration`](../videoconfiguration)
-   [`AudioConfiguration`](../audioconfiguration)
-   [`MediaCapabilities.decodingInfo()`](decodinginfo)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaCapabilities/encodingInfo" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaCapabilities/encodingInfo</a>
