# AudioConfiguration

The `AudioConfiguration` dictionary of the [Media Capabilities API](media_capabilities_api) defines the audio file being tested when calling [`MediaCapabilities.encodingInfo()`](mediacapabilities/encodinginfo) or [`MediaCapabilities.decodingInfo()`](mediacapabilities/decodinginfo) to query whether a specific audio configuration is supported, smooth, and/or power efficient.

## Properties

The `AudioConfiguration` dictionary is made up of four audio properties, including:

- **contentType**: A valid audio MIME type, For information on possible values and what they mean, see the [web audio codec guide](https://developer.mozilla.org/en-US/docs/Web/Media/Formats/Audio_codecs).
- **channels**: the number of channels used by the audio track.
- **bitrate**: The number of bits used to encode one second of the audio file.
- **samplerate**: The number of audio samples making up one second of the audio file.

## Examples

    //Create media configuration to be tested
    const mediaConfig = {
        type : 'file', // 'record', 'transmission', or 'media-source'
        audio : {
            contentType : "audio/ogg", // valid content type
            channels : 2,     // audio channels used by the track
            bitrate : 132700, // number of bits used to encode 1s of audio
            samplerate : 5200 // number of audio samples making up that 1s.
         }
    };

    // check support and performance
    navigator.mediaCapabilities.decodingInfo(mediaConfig).then(result => {
        console.log('This configuration is ' +
            (result.supported ? '' : 'not ') + 'supported, ' +
            (result.smooth ? '' : 'not ') + 'smooth, and ' +
            (result.powerEfficient ? '' : 'not ') + 'power efficient.'
    });

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/media-capabilities/#audioconfiguration">Media Capabilities<br />
<span class="small">The definition of 'AudioConfiguration' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition</td></tr></tbody></table>

## Browser compatibility

No compatibility data found for `api.AudioConfiguration`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

## See also

- [Web media technologies](https://developer.mozilla.org/en-US/docs/Web/Media)
- [Guide to media types and formats on the web](https://developer.mozilla.org/en-US/docs/Web/Media/Formats)
- [Media Capabilities API](media_capabilities_api)
- [Using the Media Capabilities API](media_capabilities_api/using_the_media_capabilities_api)
- [Media Capture and Streams API](media_streams_api)
- [MediaStream Recording API](mediastream_recording_api)
- [WebRTC](webrtc_api)
- [`MediaDecodingConfiguration`](mediadecodingconfiguration)
- [`MediaEncodingConfiguration`](mediaencodingconfiguration)
- [`VideoConfiguration`](videoconfiguration)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AudioConfiguration" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AudioConfiguration</a>
