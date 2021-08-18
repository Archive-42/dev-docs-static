VideoConfiguration
==================

The `VideoConfiguration` dictionary of the [Media Capabilities API](media_capabilities_api) is used to define the video file being tested when calling the [`MediaCapabilities`](mediacapabilities) methods [`encodingInfo()`](mediacapabilities/encodinginfo) and [`decodingInfo()`](mediacapabilities/decodinginfo) to determine whether or not the described video configuration is supported, and how smoothly and how smoooth and power-efficient it can be handled.

Properties
----------

The `VideoConfiguration` dictionary is made up of five video properties, including:

-   **contentType**: A valid video MIME type. See our [web video codec guide](https://developer.mozilla.org/en-US/docs/Web/Media/Formats/Video_codecs) for types which may be supported.
-   **width**: The width of the video.
-   **height**: The height of the video.
-   **bitrate**: The number of bits used to encode one second of the video file.
-   **framerate**: The number of frames making up one second of video playback.

Examples
--------

    // Create media configuration to be tested
    const mediaConfig = {
        type : 'file',  // see MediaDecodingConfiguration and MediaEncodingConfiguration
        video : {
            contentType : "video/webm;codecs=vp8", // valid content type
            width : 800,     // width of the video
            height : 600,    // height of the video
            bitrate : 10000, // number of bits used to encode 1s of video
            framerate : 30   // number of frames making up that 1s.
         }
    };

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/media-capabilities/#videoconfiguration">Media Capabilities<br />
<span class="small">The definition of 'VideoConfiguration' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition</td></tr></tbody></table>

Browser compatibility
---------------------

No compatibility data found for `api.VideoConfiguration`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

See also
--------

-   [Web media technologies](https://developer.mozilla.org/en-US/docs/Web/Media)
-   [Guide to media types and formats on the web](https://developer.mozilla.org/en-US/docs/Web/Media/Formats)
-   [Media Capabilities API](media_capabilities_api)
-   [Using the Media Capabilities API](media_capabilities_api/using_the_media_capabilities_api)
-   [Media Capture and Streams API](media_streams_api)
-   [MediaStream Recording API](mediastream_recording_api)
-   [WebRTC](webrtc_api)
-   [`MediaDecodingConfiguration`](mediadecodingconfiguration)
-   [`MediaEncodingConfiguration`](mediaencodingconfiguration)
-   [`AudioConfiguration`](audioconfiguration)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/VideoConfiguration" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/VideoConfiguration</a>
