# Navigator.requestMediaKeySystemAccess()

The `Navigator.requestMediaKeySystemAccess()` method returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) which delivers a [`MediaKeySystemAccess`](../mediakeysystemaccess) object that can be used to access a particular media key system, which can in turn be used to create keys for decrypting a media stream. This method is part of the [Encrypted Media Extensions API](../encrypted_media_extensions_api), which brings support for encrypted media and DRM-protected video to the web.

This method may have user-visible effects such as asking for permission to access one or more system resources. Consider that when deciding when to call ` requestMediaKeySystemAccess``() `; you don't want those requests to happen at inconvenient times. As a general rule, this function should be called only when it's about time to create and use a [`MediaKeys`](../mediakeys) object by calling the returned [`MediaKeySystemAccess`](../mediakeysystemaccess) object's [`createMediaKeys()`](../mediakeysystemaccess/createmediakeys) method.

## Syntax

    promise = navigator.requestMediaKeySystemAccess(keySystem, supportedConfigurations);

### Parameters

`keySystem`  
A [`DOMString`](../domstring) identifying the key system. For example `com.example.somesystem` or `org.w3.clearkey`.

`supportedConfigurations`  
A non-empty [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) of [`MediaKeySystemConfiguration`](../mediakeysystemconfiguration) objects. The first element with a satisfiable configuration will be used.

### Return value

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that, when resolved, delivers a [`MediaKeySystemAccess`](../mediakeysystemaccess) object to your fulfillment handler function. The fulfillment handler receives as input just one parameter:

`mediaKeySystemAccess`  
A [`MediaKeySystemAccess`](../mediakeysystemaccess) object representing the media key system configuration described by `keySystem` and `supportedConfigurations`

### Exceptions

In case of an error, the returned [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) is rejected with a [`DOMException`](../domexception) whose name indicates what kind of error occurred.

`NotSupportedError`  
Either the specified `keySystem` isn't supported by the platform or the browser, or none of the configurations specified by `supportedConfigurations` can be satisfied (if, for example, none of the `codecs` specified in `contentType` are available).

`TypeError`  
Either `keySystem` is an empty string or the `supportedConfigurations` array is empty.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/encrypted-media/#navigator-extension-requestmediakeysystemaccess">Encrypted Media Extensions<br />
<span class="small">The definition of 'requestMediaKeySystemAccess()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`requestMediaKeySystemAccess`

42

\["The spec requires that the passed `supportedConfigurations` option contain at least one of `audioCapabilities` or `videoCapabilities`, and that said parameters include a codec string.", "The function does not exist in insecure contexts. This was not enforced until Chrome 58."\]

13

38

\["Starting in Firefox 55, if neither `audioCapabilities` nor `videoCapabilities` is specified in `supportedConfigurations`, a warning is output to the web console.", "In addition, starting in Firefox 55, if in `supportedConfigurations`, either `audioCapabilities`'s or `videoCapabilities`'s `contentType` value doesn't specify a \\"codecs\\" substring to define allowed codecs within the media wrapper, a warning is output to the web console. See note below table for example and correction.", "In the future, if neither `audioCapabilities` nor `videoCapabilities` is specified in the `supportedConfigurations`, a `NotSupported` exception will be thrown."\]

No

29

\["The spec requires that the passed `supportedConfigurations` option contain at least one of `audioCapabilities` or `videoCapabilities`, and that said parameters include a codec string.", "The function does not exist in insecure contexts. This was not enforced until Opera 45."\]

13.1

43

\["The spec requires that the passed `supportedConfigurations` option contain at least one of `audioCapabilities` or `videoCapabilities`, and that said parameters include a codec string.", "The function does not exist in insecure contexts. This was not enforced until version 58."\]

42

\["The spec requires that the passed `supportedConfigurations` option contain at least one of `audioCapabilities` or `videoCapabilities`, and that said parameters include a codec string.", "The function does not exist in insecure contexts. This was not enforced until Chrome 58."\]

38

\["Starting in Firefox 55, if neither `audioCapabilities` nor `videoCapabilities` is specified in `supportedConfigurations`, a warning is output to the web console.", "In addition, starting in Firefox 55, if in `supportedConfigurations`, either `audioCapabilities`'s or `videoCapabilities`'s `contentType` value doesn't specify a \\"codecs\\" substring to define allowed codecs within the media wrapper, a warning is output to the web console. See note below table for example and correction.", "In the future, if neither `audioCapabilities` nor `videoCapabilities` is specified in the `supportedConfigurations`, a `NotSupported` exception will be thrown."\]

29

\["The spec requires that the passed `supportedConfigurations` option contain at least one of `audioCapabilities` or `videoCapabilities`, and that said parameters include a codec string.", "The function does not exist in insecure contexts. This was not enforced until Opera 45."\]

13.4

4.0

\["The spec requires that the passed `supportedConfigurations` option contain at least one of `audioCapabilities` or `videoCapabilities`, and that said parameters include a codec string.", "The function does not exist in insecure contexts. This was not enforced until Samsung Internet 7.0."\]

### Firefox compatibility notes

Firefox 55 outputs a warning to the console if a candidate [`MediaKeySystemConfiguration`](../mediakeysystemconfiguration) included in `supportedConfigurations` includes an `audioCapabilities` or `videoCapabilities` object whose value of `contentType` doesn't specify a `"codecs"` substring defining which codecs within the media wrapper format should be allowed.

For example:

    let clearKeyOptions = [
      {
        initDataTypes: ['keyids', 'webm'],
        audioCapabilities: [
          { contentType: 'audio/webm' }
        ],
        videoCapabilities: [
          { contentType: 'video/webm' }
        ]
      }
    ];

    navigator.requestMediaKeySystemAccess('org.w3.clearkey', clearKeyOptions)
    .then(function(keySystemAccess) {
      /* use the access to get create keys */
    });

The code above works in Firefox up to version 55, but version 55 onwards will output a warning to console, because `"codecs"` is not included in the `contentType` strings. This could be corrected as follows:

    let clearKeyOptions = [
      {
        initDataTypes: ['keyids', 'webm'],
        audioCapabilities: [
          { contentType: 'audio/webm; codecs="opus"' },
          { contentType: 'audio/webm; codecs="vorbis"' }
        ],
        videoCapabilities: [
          { contentType: 'video/webm; codecs="vp9"' },
          { contentType: 'video/webm; codecs="vp8"' }
        ]
      }
    ];

    navigator.requestMediaKeySystemAccess('org.w3.clearkey', clearKeyOptions)
    .then(function(keySystemAccess) {
      /* use the access to get create keys */
    });

In this revised example, the audio and video capabilities include possible codecs which should be permitted, and therefore are valid requests.

## See also

- [Encrypted Media Extensions API](../encrypted_media_extensions_api)
- [Media Capture and Streams API](../media_streams_api)
- [WebRTC API](../webrtc_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Navigator/requestMediaKeySystemAccess" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Navigator/requestMediaKeySystemAccess</a>
