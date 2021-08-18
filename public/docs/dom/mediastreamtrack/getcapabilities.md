MediaStreamTrack.getCapabilities()
==================================

The `getCapabilities()` method of the [`MediaStreamTrack`](../mediastreamtrack) interface returns a <span class="page-not-created">`MediaTrackCapabilities`</span> object which specifies the values or range of values which each constrainable property, based upon the platform and [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent).

Once you know what the browser's capabilities are, your script can use [`applyConstraints()`](applyconstraints) to ask for the track to be configured to match ideal or acceptable settings. See [Capabilities, constraints, and settings](../media_streams_api/constraints) for details on how to work with constrainable properties.

Syntax
------

    const capabilities = track.getCapabilities()

### Return value

A <span class="page-not-created">`MediaTrackCapabilities`</span> object which specifies the value or range of values which are supported for each of the user agent's supported constrainable properties.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediacapture-main/#dom-mediastreamtrack-getcapabilities">Media Capture and Streams<br />
<span class="small">The definition of 'getCapabilities()' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`getCapabilities`

66

12

No

No

53

11

66

66

No

47

11

9.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrack/getCapabilities" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrack/getCapabilities</a>
