# MediaCapabilities.decodingInfo()

The `MediaCapabilities.decodingInfo()` method, part of the [Media Capabilities API](../mediacapabilities), returns a promise with the tested media configuration's [mediaCapabilitiesInfo](mediacapabilitiesinfo); this contains the three Boolean properties `supported`, `smooth`, and `powerefficient`, which describe whether decoding the media described would be supported, smooth, and powerefficient.

## Syntax

    mediaCapabilities.decodingInfo(MediaDecodingConfiguration)

### Parameters

MediaDecodingConfiguration  
A valid [`MediaDecodingConfiguration`](../mediadecodingconfiguration) dictionary containing a valid media decoding `type` of `file` or `media-source` and a valid media configuration: either an [`AudioConfiguration`](../audioconfiguration) or a [`VideoConfiguration`](../videoconfiguration).

### Return value

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) fulfilling with a [`MediaCapabilitiesInfo`](../mediacapabilitiesinfo) interface containing three Boolean attributes:

- `supported`
- `smooth`
- `powerEfficient`

### Exceptions

A `TypeError` is raised if the `MediaConfiguration` passed to the `decodingInfo()` method is invalid, either because the type is not video or audio, the `contentType` is not a valid codec MIME type, the media decoding configuration is not a valid value for the [media decoding type](../mediadecodingtype), or any other error in the media configuration passed to the method, including omitting values required in the [media decoding configuration](../mediadecodingconfiguration).

## Example

    //Create media configuration to be tested
    const mediaConfig = {
        type : 'file', // or 'media-source'
        audio : {
            contentType : "audio/ogg", // valid content type
            channels : 2,     // audio channels used by the track
            bitrate : 132700, // number of bits used to encode 1s of audio
            samplerate : 5200 // number of audio samples making up that 1s.
         },
    };

    // check support and performance
    navigator.mediaCapabilities.decodingInfo(mediaConfig).then(result => {
        console.log('This configuration is ' +
            (result.supported ? '' : 'not ') + 'supported, ' +
            (result.smooth ? '' : 'not ') + 'smooth, and ' +
            (result.powerEfficient ? '' : 'not ') + 'power efficient.')
    });

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/media-capabilities/#dom-mediacapabilities-decodinginfo-configuration-configuration">Media Capabilities<br />
<span class="small">The definition of 'decodingInfo()' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition</td></tr></tbody></table>

## Browser compatibility

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

## See also

- [`MediaDecodingConfiguration`](../mediadecodingconfiguration)
- [`VideoConfiguration`](../videoconfiguration)
- [`AudioConfiguration`](../audioconfiguration)
- [`MediaCapabilities.encodingInfo()`](encodinginfo)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaCapabilities/decodingInfo" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaCapabilities/decodingInfo</a>
