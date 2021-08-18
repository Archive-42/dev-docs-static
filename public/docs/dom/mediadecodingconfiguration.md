# MediaDecodingConfiguration

The `MediaDecodingConfiguration` dictionary of the [Media Capabilities API](media_capabilities_api) is used to define the type of media being tested when calling [`MediaCapabilities.decodingInfo()`](mediacapabilities/decodinginfo) to query whether a specific media configuration is supported, smooth, and/or power efficient.

## Properties

A `MediaDecodingConfiguration` dictionary takes two properties:

- `type` — the type of media being tested. This takes one of two values:
  - `file`: Represents a configuration that is meant to be used for a plain file playback.
  - `media-source`: Represents a configuration that is meant to be used for playback of a [`MediaSource`](mediasource).
- A media configuration — a [`VideoConfiguration`](videoconfiguration) or [`AudioConfiguration`](audioconfiguration) dictionary.

## Examples

    //Create media configuration to be tested
    const mediaConfig = {
        type : 'file', // or 'media-source'
        video : {
            contentType : "video/webm;codecs=vp8", // valid content type
            width : 800,     // width of the video
            height : 600,    // height of the video
            bitrate : 10000, // number of bits used to encode 1s of video
            framerate : 30   // number of frames making up that 1s.
         }
    };

    // check support and performance
    navigator.mediaCapabilities.decodingInfo(mediaConfig).then(result => {
        console.log('This configuration is ' +  (result.supported ? '' : 'not ') + 'supported.')
    });

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/media-capabilities/#mediaconfiguration">Media Capabilities<br />
<span class="small">The definition of 'MediaDecodingConfiguration' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition</td></tr></tbody></table>

## Browser compatibility

No compatibility data found for `api.MediaDecodingConfiguration`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

## See also

- [`MediaConfiguration`](mediaconfiguration)
- [`MediaEncodingConfiguration`](mediaencodingconfiguration)
- [`HTMLMediaElement.canPlayType()`](htmlmediaelement/canplaytype) for file
- [`MediaSource.isTypeSupported()`](mediasource/istypesupported) for media-source

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaDecodingConfiguration" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaDecodingConfiguration</a>
