Navigator.mediaCapabilities
===========================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `Navigator.mediaCapabilities` read-only property returns a [`MediaCapabilities`](../mediacapabilities) object that can expose information about the decoding and encoding capabilities for a given format and output capabilities as defined by the [Media Capabilities API](../media_capabilities_api).

Syntax
------

    mediaCapabilitiesObj = globalObj.navigator.mediaCapabilities

Value
-----

A [`MediaCapabilities`](../mediacapabilities) object.

Examples
--------

    navigator.mediaCapabilities.decodingInfo({
        type : 'file',
        audio : {
            contentType : "audio/mp3",
            channels : 2,
            bitrate : 132700,
            samplerate : 5200
        }
    }).then(function(result) {
      console.log('This configuration is ' +
            (result.supported ? '' : 'not ') + 'supported, ' +
            (result.smooth ? '' : 'not ') + 'smooth, and ' +
            (result.powerEfficient ? '' : 'not ') + 'power efficient.')
    });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/media-capabilities/">Media Capabilities</a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`mediaCapabilities`

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

See also
--------

-   [Media Capabilities API](../media_capabilities_api)
-   [`Navigator`](../navigator)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Navigator/mediaCapabilities" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Navigator/mediaCapabilities</a>
