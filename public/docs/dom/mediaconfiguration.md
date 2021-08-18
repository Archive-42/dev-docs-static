MediaConfiguration
==================

The `MediaConfiguration` [`MediaCapabilities`](mediacapabilities) dictionary of the [Media Capabilities API](mediacapabilities) describes how media and audio files must be configured, or defined, to be passed as a parameter of the [`MediaCapabilities.encodingInfo()`](mediacapabilities/encodinginfo) and [`MediaCapabilities.encodingInfo()`](mediacapabilities/encodinginfo) methods.

Properties
----------

A valid configuration includes a valid encoding configuration type or decoding configuration type and a valid [audio configuration](audioconfiguration) or [video configuration](videoconfiguration). If you plan on querying [encoding](mediaencodingconfiguration) information, set the media type to record or transmission.

For [decoding](mediadecodingconfiguration), set the type to `file` or `media-source`.

If the media is an audio file, the [audio configuration](audioconfiguration) must include a valid audio MIME type as `contentType`, the number of channels, the bitrate, and the sample rate. [Video configurations](videoconfiguration) mush include a valid video MIME type as contentType, the bitrate, and framerate, along with the width and the height of the video file. All of these must be present, as in the examples below, or a TypeError will occur.

A valid media decoding configuration, to be submitted as the parameter for [`mediaCapabilities.decodingInfo()`](mediacapabilities/decodinginfo) method, has it's \`type\` set as:

-   **file**: For plain playback file.
-   **media-source**: For [media source](mediasource) files.

A valid media encoding configuration, to be submitted as the parameter for [`mediaCapabilities.encodingInfo()`](mediacapabilities/encodinginfo) method, has it's \`type\` set as:

-   **record**: For [recording media](mediarecorder).
-   **transmission**: For media to be electronically transmitted.

A valid [audio configuration](audioconfiguration) includes:

-   **contentType**: Valid audio MIME type.
-   **channels**: Number of channels used by the audio track.
-   **bitrate**: Number of bits used to encode one second of the audio file.
-   **samplerate**: Number of audio samples making up one second of the audio file.

A valid [video configuration](videoconfiguration) includes:

-   **contentType**: Valid video MIME type.
-   **width**: Width of the video.
-   **height**: Height of the video.
-   **bitrate**: Number of bits used to encode one second of the video file.
-   **framerate**: Number of frames making up one second of video playback.

Example
-------

    //Create a video configuration to be tested
    const videoDecoderConfig = {
      type : 'file', // 'record', 'transmission', or 'media-source'
      video : {
        contentType : "video/webm;codecs=vp8", // valid content type
        width : 800,     // width of the video
        height : 600,    // height of the video
        bitrate : 10000, // number of bits used to encode 1s of video
        framerate : 30   // number of frames making up that 1s.
      }
    };

    const audioEncoderConfig = {
      type : 'file', // 'record', 'transmission', or 'media-source'
      audio : {
        contentType : "audio/ogg", // valid content type
        channels : 2,     // audio channels used by the track
        bitrate : 132700, // number of bits used to encode 1s of audio
        samplerate : 5200 // number of audio samples making up that 1s.
      }
    };

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/media-capabilities/#mediaconfiguration">Media Capabilities<br />
<span class="small">The definition of 'MediaConfiguration' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition</td></tr></tbody></table>

Browser compatibility
---------------------

No compatibility data found for `api.MediaConfiguration`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

See also
--------

-   [`MediaDecodingConfiguration`](mediadecodingconfiguration)
-   [`MediaEncodingConfiguration`](mediaencodingconfiguration)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaConfiguration" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaConfiguration</a>
