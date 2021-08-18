Feature-Policy
==============

The HTTP `Feature-Policy` header provides a mechanism to allow and deny the use of browser features in its own frame, and in content within any [`<iframe>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe) elements in the document.

This header is still in an experimental state, and is subject to change at any time. Be wary of this when implementing it on your website. The header has now been renamed to `Permissions-Policy` in the spec, and this article will eventually be updated to reflect that change.

For more information, see the main [Feature Policy](https://developer.mozilla.org/docs/Web/HTTP/Feature_Policy) article.

<table><tbody><tr class="odd"><td>Header type</td><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Response_header">Response header</a></td></tr><tr class="even"><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Forbidden_header_name">Forbidden header name</a></td><td>yes</td></tr></tbody></table>

Syntax
------

    Feature-Policy: <directive> <allowlist>

`<directive>`  
The Feature Policy directive to apply the `allowlist` to. See [Directives](#Directives) below for a list of the permitted directive names.

`<allowlist>`  
An `allowlist` is a list of origins that takes one or more of the following values, separated by spaces:

-   `*`: The feature will be allowed in this document, and all nested browsing contexts (iframes) regardless of their origin.
-   `'self'`: The feature will be allowed in this document, and in all nested browsing contexts (iframes) in the same origin.
-   `'src'`: (In an iframe `allow` attribute only) The feature will be allowed in this iframe, as long as the document loaded into it comes from the same origin as the URL in the iframe's [src](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe#Attributes) attribute.
    The `'src'` origin is used in the iframe `allow` attribute only, and is the *default* `allowlist` value.

-   `'none'`: The feature is disabled in top-level and nested browsing contexts.
-   &lt;origin(s)&gt;: The feature is allowed for specific origins (for example, https://example.com). Origins should be separated by a space.

The values `*` (enable for all origins) or `'none'` (disable for all origins) may only be used alone, while `'self'` and `'src'` may be used with one or more origins.

Features are each defined to have a default allowlist, which is one of:

-   `*`: The feature is allowed by default in top-level browsing contexts and all nested browsing contexts (iframes).
-   `'self'`: The feature is allowed by default in top-level browsing contexts and in nested browsing contexts (iframes) in the same origin. The feature is not allowed in cross-origin documents in nested browsing contexts.
-   `'none'`: The feature is disabled in top-level and nested browsing contexts.

Directives
----------

[`accelerometer`](feature-policy/accelerometer)  
Controls whether the current document is allowed to gather information about the acceleration of the device through the [`Accelerometer`](https://developer.mozilla.org/en-US/docs/Web/API/Accelerometer) interface.

[`ambient-light-sensor`](feature-policy/ambient-light-sensor)  
Controls whether the current document is allowed to gather information about the amount of light in the environment around the device through the [`AmbientLightSensor`](https://developer.mozilla.org/en-US/docs/Web/API/AmbientLightSensor) interface.

[`autoplay`](feature-policy/autoplay)  
Controls whether the current document is allowed to autoplay media requested through the [`HTMLMediaElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement) interface. When this policy is disabled and there were no user gestures, the [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) returned by [`HTMLMediaElement.play()`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/play) will reject with a [`DOMException`](https://developer.mozilla.org/en-US/docs/Web/API/DOMException). The autoplay attribute on [`<audio>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/audio) and [`<video>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video) elements will be ignored.

[`battery`](feature-policy/battery)  
Controls whether the use of the [Battery Status API](https://developer.mozilla.org/docs/Web/API/Battery_Status_API) is allowed. When this policy is disabled, the [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) returned by [`Navigator.getBattery()`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/getBattery) will reject with a [`NotAllowedError`](https://developer.mozilla.org/en-US/docs/Web/API/DOMException#exception-NotAllowedError) [`DOMException`](https://developer.mozilla.org/en-US/docs/Web/API/DOMException).

[`camera`](feature-policy/camera)  
Controls whether the current document is allowed to use video input devices. When this policy is disabled, the [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) returned by [`getUserMedia()`](https://developer.mozilla.org/en-US/docs/Web/API/MediaDevices/getUserMedia) will reject with a [`NotAllowedError`](https://developer.mozilla.org/en-US/docs/Web/API/DOMException#exception-NotAllowedError) [`DOMException`](https://developer.mozilla.org/en-US/docs/Web/API/DOMException).

[`display-capture`](feature-policy/display-capture)  
Controls whether or not the current document is permitted to use the [`getDisplayMedia()`](https://developer.mozilla.org/en-US/docs/Web/API/MediaDevices/getDisplayMedia) method to capture screen contents. When this policy is disabled, the promise returned by `getDisplayMedia()` will reject with a [`NotAllowedError`](https://developer.mozilla.org/en-US/docs/Web/API/DOMException#exception-NotAllowedError) if permission is not obtained to capture the display's contents.

[`document-domain`](feature-policy/document-domain)  
Controls whether the current document is allowed to set [`document.domain`](https://developer.mozilla.org/en-US/docs/Web/API/Document/domain). When this policy is disabled, attempting to set [`document.domain`](https://developer.mozilla.org/en-US/docs/Web/API/Document/domain) will fail and cause a [`SecurityError`](https://developer.mozilla.org/en-US/docs/Web/API/DOMException#exception-SecurityError) [`DOMException`](https://developer.mozilla.org/en-US/docs/Web/API/DOMException) to be be thrown.

[`encrypted-media`](feature-policy/encrypted-media)  
Controls whether the current document is allowed to use the [Encrypted Media Extensions](https://developer.mozilla.org/en-US/docs/Web/API/Encrypted_Media_Extensions_API) API (EME). When this policy is disabled, the [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) returned by [`Navigator.requestMediaKeySystemAccess()`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/requestMediaKeySystemAccess) will reject with a [`DOMException`](https://developer.mozilla.org/en-US/docs/Web/API/DOMException).

[`execution-while-not-rendered`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Feature-Policy/execution-while-not-rendered)  
Controls whether tasks should execute in frames while they're not being rendered (e.g. if an iframe is `hidden` or `display: none`).

[`execution-while-out-of-viewport`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Feature-Policy/execution-while-out-of-viewport)  
Controls whether tasks should execute in frames while they're outside of the visible viewport.

<!-- -->

[`fullscreen`](feature-policy/fullscreen)  
Controls whether the current document is allowed to use [`Element.requestFullScreen()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/requestFullScreen). When this policy is disabled, the returned [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) rejects with a [`TypeError`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypeError).

[`geolocation`](feature-policy/geolocation)  
Controls whether the current document is allowed to use the [`Geolocation`](https://developer.mozilla.org/en-US/docs/Web/API/Geolocation) Interface. When this policy is disabled, calls to [`getCurrentPosition()`](https://developer.mozilla.org/en-US/docs/Web/API/Geolocation/getCurrentPosition) and [`watchPosition()`](https://developer.mozilla.org/en-US/docs/Web/API/Geolocation/watchPosition) will cause those functions' callbacks to be invoked with a [`PositionError`](https://developer.mozilla.org/en-US/docs/Web/API/PositionError) code of `PERMISSION_DENIED`.

[`gyroscope`](feature-policy/gyroscope)  
Controls whether the current document is allowed to gather information about the orientation of the device through the [`Gyroscope`](https://developer.mozilla.org/en-US/docs/Web/API/Gyroscope) interface.

[`layout-animations`](feature-policy/layout-animations)  
Controls whether the current document is allowed to show layout animations.

<!-- -->

[`legacy-image-formats`](feature-policy/legacy-image-formats)  
Controls whether the current document is allowed to display images in legacy formats.

<!-- -->

[`magnetometer`](feature-policy/magnetometer)  
Controls whether the current document is allowed to gather information about the orientation of the device through the [`Magnetometer`](https://developer.mozilla.org/en-US/docs/Web/API/Magnetometer) interface.

[`microphone`](feature-policy/microphone)  
Controls whether the current document is allowed to use audio input devices. When this policy is disabled, the [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) returned by [`MediaDevices.getUserMedia()`](https://developer.mozilla.org/en-US/docs/Web/API/MediaDevices/getUserMedia) will reject with a [`NotAllowedError`](https://developer.mozilla.org/en-US/docs/Web/API/DOMException#exception-NotAllowedError).

[`midi`](feature-policy/midi)  
Controls whether the current document is allowed to use the [Web MIDI API](https://developer.mozilla.org/en-US/docs/Web/API/Web_MIDI_API). When this policy is disabled, the [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) returned by [`Navigator.requestMIDIAccess()`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/requestMIDIAccess) will reject with a [`DOMException`](https://developer.mozilla.org/en-US/docs/Web/API/DOMException).

[`navigation-override`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Feature-Policy/navigation-override)  
Controls the availability of mechanisms that enables the page author to take control over the behavior of [spatial navigation](https://www.w3.org/TR/css-nav/), or to cancel it outright.

[`oversized-images`](feature-policy/oversized-images)  
Controls whether the current document is allowed to download and display large images.

[`payment`](feature-policy/payment)  
Controls whether the current document is allowed to use the [Payment Request API](https://developer.mozilla.org/en-US/docs/Web/API/Payment_Request_API). When this policy is enabled, the [`PaymentRequest()`](https://developer.mozilla.org/en-US/docs/Web/API/PaymentRequest) constructor will throw a [`SecurityError`](https://developer.mozilla.org/en-US/docs/Web/API/DOMException#exception-SecurityError) [`DOMException`](https://developer.mozilla.org/en-US/docs/Web/API/DOMException).

[`picture-in-picture`](feature-policy/picture-in-picture)  
Controls whether the current document is allowed to play a video in a Picture-in-Picture mode via the corresponding API.

[`publickey-credentials-get`](feature-policy/publickey-credentials-get)  
Controls whether the current document is allowed to use the [Web Authentication API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Authentication_API) to retreive already stored public-key credentials, i.e. via [`navigator.credentials.get({publicKey: ..., ...})`](https://developer.mozilla.org/en-US/docs/Web/API/CredentialsContainer/get).

[`sync-xhr`](feature-policy/sync-xhr)  
Controls whether the current document is allowed to make synchronous [`XMLHttpRequest`](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest) requests.

[`usb`](feature-policy/usb)  
Controls whether the current document is allowed to use the [WebUSB API](https://wicg.github.io/webusb/).

 [`vr`](feature-policy/vr)   
Controls whether the current document is allowed to use the [WebVR API](https://developer.mozilla.org/en-US/docs/Web/API/WebVR_API). When this policy is disabled, the [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) returned by [`Navigator.getVRDisplays()`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/getVRDisplays) will reject with a [`DOMException`](https://developer.mozilla.org/en-US/docs/Web/API/DOMException). Keep in mind that the WebVR standard is in the process of being replaced with [WebXR](https://developer.mozilla.org/en-US/docs/Web/API/WebXR_Device_API).

[`wake-lock`](feature-policy/wake-lock)  
Controls whether the current document is allowed to use [Wake Lock API](https://www.w3.org/TR/wake-lock/) to indicate that device should not enter power-saving mode.

[`screen-wake-lock`](feature-policy/screen-wake-lock)  
Controls whether the current document is allowed to use [Screen Wake Lock API](https://developer.mozilla.org/en-US/docs/Web/API/Screen_Wake_Lock_API) to indicate that device should not turn off or dim the screen.

[`web-share`](feature-policy/web-share)  
Controls whether or not the current document is allowed to use the [`Navigator.share()`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/share) of Web Share API to share text, links, images, and other content to arbitrary destinations of user's choice, e.g. mobile apps.

[`xr-spatial-tracking`](feature-policy/xr-spatial-tracking)  
Controls whether or not the current document is allowed to use the [WebXR Device API](https://developer.mozilla.org/en-US/docs/Web/API/WebXR_Device_API) to interact with a WebXR session.

Example
-------

SecureCorp Inc. wants to disable Microphone and Geolocation APIs in its application. It can do so by delivering the following HTTP response header to define a feature policy:

    Feature-Policy: microphone 'none'; geolocation 'none'

By specifying the `'none'` keyword for the origin list, the specified features will be disabled for all browsing contexts (this includes all iframes), regardless of their origin.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webappsec-permissions-policy/#permissions-policy-http-header-field">Permissions Policy</a></td></tr></tbody></table>

Browser compatibility<a href="https://github.com/mdn/browser-compat-data" class="bc-github-link">Update compatibility data on GitHub</a>
----------------------------------------------------------------------------------------------------------------------------------------

Desktop

<span class="bc-head-txt-label bc-head-icon-chrome">Chrome</span>

<span class="bc-head-txt-label bc-head-icon-edge">Edge</span>

<span class="bc-head-txt-label bc-head-icon-firefox">Firefox</span>

<span class="bc-head-txt-label bc-head-icon-ie">Internet Explorer</span>

<span class="bc-head-txt-label bc-head-icon-opera">Opera</span>

<span class="bc-head-txt-label bc-head-icon-safari">Safari</span>

`Feature-Policy`

60

79

74

74

65

Disabled

Disabled From version 65: this feature is behind the `dom.security.featurePolicy.header.enabled` preference (needs to be set to `true`). To change preferences in Firefox, visit about:config.

No

47

11.1

11.1   
Only supported through the `allow` attribute on `<iframe>` elements.

[`accelerometer`](feature-policy/accelerometer)

69

Disabled

69

Disabled

Disabled From version 69: this feature is behind the `#enable-experimental-productivity-features` preference (needs to be set to `Enabled`). To change preferences in Chrome, visit chrome://flags.

79

Disabled

79

Disabled

Disabled From version 79: this feature is behind the `#enable-experimental-productivity-features` preference (needs to be set to `Enabled`).

No

No

56

Disabled

56

Disabled

Disabled From version 56: this feature is behind the `#enable-experimental-productivity-features` preference (needs to be set to `Enabled`).

No

[`ambient-light-sensor`](feature-policy/ambient-light-sensor)

69

Disabled

69

Disabled

Disabled From version 69: this feature is behind the `#enable-experimental-productivity-features` preference (needs to be set to `Enabled`). To change preferences in Chrome, visit chrome://flags.

79

Disabled

79

Disabled

Disabled From version 79: this feature is behind the `#enable-experimental-productivity-features` preference (needs to be set to `Enabled`).

No

No

56

Disabled

56

Disabled

Disabled From version 56: this feature is behind the `#enable-experimental-productivity-features` preference (needs to be set to `Enabled`).

No

[`autoplay`](feature-policy/autoplay)

64

79

74

74

65

Disabled

Disabled From version 65: this feature is behind the `dom.security.featurePolicy.header.enabled` preference (needs to be set to `true`). To change preferences in Firefox, visit about:config.

No

51

No

[`battery`](feature-policy/battery)

No

 No   
Will be implemented, see [bug 1007264](https://crbug.com/1007264).

No

 No   
Will be implemented, see [bug 1007264](https://crbug.com/1007264).

No

No

No

No

[`camera`](feature-policy/camera)

60

79

74

74

65

Disabled

Disabled From version 65: this feature is behind the `dom.security.featurePolicy.header.enabled` preference (needs to be set to `true`). To change preferences in Firefox, visit about:config.

No

48

11.1

[`display-capture`](feature-policy/display-capture)

No

No

74

74

67

Disabled

Disabled From version 67: this feature is behind the `dom.security.featurePolicy.header.enabled` preference (needs to be set to `true`). To change preferences in Firefox, visit about:config.

No

No

No

[`document-domain`](feature-policy/document-domain)

77

79

74

74

65

Disabled

Disabled From version 65: this feature is behind the `dom.security.featurePolicy.header.enabled` preference (needs to be set to `true`). To change preferences in Firefox, visit about:config.

No

64

No

[`encrypted-media`](feature-policy/encrypted-media)

60

79

74

74

65

Disabled

Disabled From version 65: this feature is behind the `dom.security.featurePolicy.header.enabled` preference (needs to be set to `true`). To change preferences in Firefox, visit about:config.

No

48

No

[`fullscreen`](feature-policy/fullscreen)

62

79

74

74

Before Firefox 80, applying `fullscreen` to an `<iframe>` (i.e. via the `allow` attribute) does not work unless the `allowfullscreen` attribute is also present.

65

Disabled

Disabled From version 65: this feature is behind the `dom.security.featurePolicy.header.enabled` preference (needs to be set to `true`). To change preferences in Firefox, visit about:config.

No

49

No

[`geolocation`](feature-policy/geolocation)

60

79

74

74

65

Disabled

Disabled From version 65: this feature is behind the `dom.security.featurePolicy.header.enabled` preference (needs to be set to `true`). To change preferences in Firefox, visit about:config.

No

47

No

[`gyroscope`](feature-policy/gyroscope)

69

Disabled

69

Disabled

Disabled From version 69: this feature is behind the `#enable-experimental-productivity-features` preference (needs to be set to `Enabled`). To change preferences in Chrome, visit chrome://flags.

79

Disabled

79

Disabled

Disabled From version 79: this feature is behind the `#enable-experimental-productivity-features` preference (needs to be set to `Enabled`).

No

No

56

Disabled

56

Disabled

Disabled From version 56: this feature is behind the `#enable-experimental-productivity-features` preference (needs to be set to `Enabled`).

No

[`layout-animations`](feature-policy/layout-animations)

No

No

No

No

No

No

[`legacy-image-formats`](feature-policy/legacy-image-formats)

68

Disabled

68

Disabled

Disabled From version 68: this feature is behind the `#enable-experimental-productivity-features` preference (needs to be set to `Enabled`). To change preferences in Chrome, visit chrome://flags.

79

Disabled

79

Disabled

Disabled From version 79: this feature is behind the `#enable-experimental-productivity-features` preference (needs to be set to `Enabled`).

No

No

55

Disabled

55

Disabled

Disabled From version 55: this feature is behind the `#enable-experimental-productivity-features` preference (needs to be set to `Enabled`).

No

[`magnetometer`](feature-policy/magnetometer)

69

Disabled

69

Disabled

Disabled From version 69: this feature is behind the `#enable-experimental-productivity-features` preference (needs to be set to `Enabled`). To change preferences in Chrome, visit chrome://flags.

79

Disabled

79

Disabled

Disabled From version 79: this feature is behind the `#enable-experimental-productivity-features` preference (needs to be set to `Enabled`).

No

No

56

Disabled

56

Disabled

Disabled From version 56: this feature is behind the `#enable-experimental-productivity-features` preference (needs to be set to `Enabled`).

No

[`microphone`](feature-policy/microphone)

60

79

74

74

65

Disabled

Disabled From version 65: this feature is behind the `dom.security.featurePolicy.header.enabled` preference (needs to be set to `true`). To change preferences in Firefox, visit about:config.

No

48

11.1

[`midi`](feature-policy/midi)

60

79

74

74

65

Disabled

Disabled From version 65: this feature is behind the `dom.security.featurePolicy.header.enabled` preference (needs to be set to `true`). To change preferences in Firefox, visit about:config.

No

47

No

[`oversized-images`](feature-policy/oversized-images)

72

Disabled

72

Disabled

Disabled From version 72: this feature is behind the `#enable-experimental-productivity-features` preference (needs to be set to `Enabled`). To change preferences in Chrome, visit chrome://flags.

79

Disabled

79

Disabled

Disabled From version 79: this feature is behind the `#enable-experimental-productivity-features` preference (needs to be set to `Enabled`).

No

No

60

Disabled

60

Disabled

Disabled From version 60: this feature is behind the `#enable-experimental-productivity-features` preference (needs to be set to `Enabled`).

No

[`payment`](feature-policy/payment)

60

79

74

74

65

Disabled

Disabled From version 65: this feature is behind the `dom.security.featurePolicy.header.enabled` preference (needs to be set to `true`). To change preferences in Firefox, visit about:config.

No

47

No

[`picture-in-picture`](feature-policy/picture-in-picture)

No

No

No

No

No

No

[`publickey-credentials-get`](feature-policy/publickey-credentials-get)

84

84

No

No

No

No

[`sync-xhr`](feature-policy/sync-xhr)

65

79

No

No

52

No

[`unoptimized-images`](feature-policy/unoptimized-images)

72

Disabled

72

Disabled

Disabled From version 72: this feature is behind the `#enable-experimental-productivity-features` preference (needs to be set to `Enabled`). To change preferences in Chrome, visit chrome://flags.

79

Disabled

79

Disabled

Disabled From version 79: this feature is behind the `#enable-experimental-productivity-features` preference (needs to be set to `Enabled`).

No

No

60

Disabled

60

Disabled

Disabled From version 60: this feature is behind the `#enable-experimental-productivity-features` preference (needs to be set to `Enabled`).

No

[`unsized-media`](feature-policy/unsized-media)

66

Disabled

66

Disabled

Disabled From version 66: this feature is behind the `#enable-experimental-productivity-features` preference (needs to be set to `Enabled`). To change preferences in Chrome, visit chrome://flags.

79

Disabled

79

Disabled

Disabled From version 79: this feature is behind the `#enable-experimental-productivity-features` preference (needs to be set to `Enabled`).

No

No

53

Disabled

53

Disabled

Disabled From version 53: this feature is behind the `#enable-experimental-productivity-features` preference (needs to be set to `Enabled`).

No

[`usb`](feature-policy/usb)

60

79

No

No

47

No

[`vibrate`](feature-policy/vibrate)

No

No

No

No

No

No

[`vr`](feature-policy/vr)

62 — 80

62 — 80   
WebVR API was never enabled by default in any production builds and was replaced by WebXR Device API.

79 — 80

79 — 80   
WebVR API was never enabled by default in any production builds and was replaced by WebXR Device API.

No

No

49 — 67

49 — 67   
WebVR API was never enabled by default in any production builds and was replaced by WebXR Device API.

No

[`wake-lock`](feature-policy/wake-lock)

No

No

No

No

No

No

[`xr-spatial-tracking`](feature-policy/xr-spatial-tracking)

79

79

No

No

66

No

Mobile

<span class="bc-head-txt-label bc-head-icon-webview_android">Android webview</span>

<span class="bc-head-txt-label bc-head-icon-chrome_android">Chrome for Android</span>

<span class="bc-head-txt-label bc-head-icon-firefox_android">Firefox for Android</span>

<span class="bc-head-txt-label bc-head-icon-opera_android">Opera for Android</span>

<span class="bc-head-txt-label bc-head-icon-safari_ios">Safari on iOS</span>

<span class="bc-head-txt-label bc-head-icon-samsunginternet_android">Samsung Internet</span>

`Feature-Policy`

60

60

65

Disabled

65

Disabled

Disabled From version 65: this feature is behind the `dom.security.featurePolicy.header.enabled` preference (needs to be set to `true`). To change preferences in Firefox, visit about:config.

44

11.3

11.3   
Only supported through the `allow` attribute on `<iframe>` elements.

8.0

[`accelerometer`](feature-policy/accelerometer)

No

69

Disabled

69

Disabled

Disabled From version 69: this feature is behind the `#enable-experimental-productivity-features` preference (needs to be set to `Enabled`). To change preferences in Chrome, visit chrome://flags.

No

48

Disabled

48

Disabled

Disabled From version 48: this feature is behind the `#enable-experimental-productivity-features` preference (needs to be set to `Enabled`).

No

No

[`ambient-light-sensor`](feature-policy/ambient-light-sensor)

No

69

Disabled

69

Disabled

Disabled From version 69: this feature is behind the `#enable-experimental-productivity-features` preference (needs to be set to `Enabled`). To change preferences in Chrome, visit chrome://flags.

No

48

Disabled

48

Disabled

Disabled From version 48: this feature is behind the `#enable-experimental-productivity-features` preference (needs to be set to `Enabled`).

No

No

[`autoplay`](feature-policy/autoplay)

64

64

65

Disabled

65

Disabled

Disabled From version 65: this feature is behind the `dom.security.featurePolicy.header.enabled` preference (needs to be set to `true`). To change preferences in Firefox, visit about:config.

47

No

9.0

[`battery`](feature-policy/battery)

No

No

 No   
Will be implemented, see [bug 1007264](https://crbug.com/1007264).

No

No

No

No

[`camera`](feature-policy/camera)

60

60

65

Disabled

65

Disabled

Disabled From version 65: this feature is behind the `dom.security.featurePolicy.header.enabled` preference (needs to be set to `true`). To change preferences in Firefox, visit about:config.

45

11.3

8.0

[`display-capture`](feature-policy/display-capture)

No

No

67

Disabled

67

Disabled

Disabled From version 67: this feature is behind the `dom.security.featurePolicy.header.enabled` preference (needs to be set to `true`). To change preferences in Firefox, visit about:config.

No

No

No

[`document-domain`](feature-policy/document-domain)

No

No

65

Disabled

65

Disabled

Disabled From version 65: this feature is behind the `dom.security.featurePolicy.header.enabled` preference (needs to be set to `true`). To change preferences in Firefox, visit about:config.

No

No

No

[`encrypted-media`](feature-policy/encrypted-media)

60

60

65

Disabled

65

Disabled

Disabled From version 65: this feature is behind the `dom.security.featurePolicy.header.enabled` preference (needs to be set to `true`). To change preferences in Firefox, visit about:config.

45

No

8.0

[`fullscreen`](feature-policy/fullscreen)

62

62

65

Disabled

65

Disabled

Disabled From version 65: this feature is behind the `dom.security.featurePolicy.header.enabled` preference (needs to be set to `true`). To change preferences in Firefox, visit about:config.

46

No

8.0

[`geolocation`](feature-policy/geolocation)

60

60

65

Disabled

65

Disabled

Disabled From version 65: this feature is behind the `dom.security.featurePolicy.header.enabled` preference (needs to be set to `true`). To change preferences in Firefox, visit about:config.

44

No

8.0

[`gyroscope`](feature-policy/gyroscope)

No

69

Disabled

69

Disabled

Disabled From version 69: this feature is behind the `#enable-experimental-productivity-features` preference (needs to be set to `Enabled`). To change preferences in Chrome, visit chrome://flags.

No

48

Disabled

48

Disabled

Disabled From version 48: this feature is behind the `#enable-experimental-productivity-features` preference (needs to be set to `Enabled`).

No

No

[`layout-animations`](feature-policy/layout-animations)

No

No

No

No

No

No

[`legacy-image-formats`](feature-policy/legacy-image-formats)

No

68

Disabled

68

Disabled

Disabled From version 68: this feature is behind the `#enable-experimental-productivity-features` preference (needs to be set to `Enabled`). To change preferences in Chrome, visit chrome://flags.

No

48

Disabled

48

Disabled

Disabled From version 48: this feature is behind the `#enable-experimental-productivity-features` preference (needs to be set to `Enabled`).

No

No

[`magnetometer`](feature-policy/magnetometer)

No

69

Disabled

69

Disabled

Disabled From version 69: this feature is behind the `#enable-experimental-productivity-features` preference (needs to be set to `Enabled`). To change preferences in Chrome, visit chrome://flags.

No

48

Disabled

48

Disabled

Disabled From version 48: this feature is behind the `#enable-experimental-productivity-features` preference (needs to be set to `Enabled`).

No

No

[`microphone`](feature-policy/microphone)

60

60

65

Disabled

65

Disabled

Disabled From version 65: this feature is behind the `dom.security.featurePolicy.header.enabled` preference (needs to be set to `true`). To change preferences in Firefox, visit about:config.

45

11.3

8.0

[`midi`](feature-policy/midi)

60

60

65

Disabled

65

Disabled

Disabled From version 65: this feature is behind the `dom.security.featurePolicy.header.enabled` preference (needs to be set to `true`). To change preferences in Firefox, visit about:config.

44

No

8.0

[`oversized-images`](feature-policy/oversized-images)

No

72

Disabled

72

Disabled

Disabled From version 72: this feature is behind the `#enable-experimental-productivity-features` preference (needs to be set to `Enabled`). To change preferences in Chrome, visit chrome://flags.

No

50

Disabled

50

Disabled

Disabled From version 50: this feature is behind the `#enable-experimental-productivity-features` preference (needs to be set to `Enabled`).

No

No

[`payment`](feature-policy/payment)

60

60

65

Disabled

65

Disabled

Disabled From version 65: this feature is behind the `dom.security.featurePolicy.header.enabled` preference (needs to be set to `true`). To change preferences in Firefox, visit about:config.

44

No

8.0

[`picture-in-picture`](feature-policy/picture-in-picture)

No

No

No

No

No

No

[`publickey-credentials-get`](feature-policy/publickey-credentials-get)

84

84

No

No

No

No

[`sync-xhr`](feature-policy/sync-xhr)

65

65

No

47

No

9.0

[`unoptimized-images`](feature-policy/unoptimized-images)

No

72

Disabled

72

Disabled

Disabled From version 72: this feature is behind the `#enable-experimental-productivity-features` preference (needs to be set to `Enabled`). To change preferences in Chrome, visit chrome://flags.

No

50

Disabled

50

Disabled

Disabled From version 50: this feature is behind the `#enable-experimental-productivity-features` preference (needs to be set to `Enabled`).

No

No

[`unsized-media`](feature-policy/unsized-media)

No

66

Disabled

66

Disabled

Disabled From version 66: this feature is behind the `#enable-experimental-productivity-features` preference (needs to be set to `Enabled`). To change preferences in Chrome, visit chrome://flags.

No

47

Disabled

47

Disabled

Disabled From version 47: this feature is behind the `#enable-experimental-productivity-features` preference (needs to be set to `Enabled`).

No

9.0

[`usb`](feature-policy/usb)

60

60

No

44

No

8.0

[`vibrate`](feature-policy/vibrate)

No

No

No

No

No

No

[`vr`](feature-policy/vr)

No

62 — 80

62 — 80   
WebVR API was never enabled by default in any production builds and was replaced by WebXR Device API.

No

46 — ?

46 — ?   
WebVR API was never enabled by default in any production builds and was replaced by WebXR Device API.

No

8.0 — ?

8.0 — ?   
WebVR API was never enabled by default in any production builds and was replaced by WebXR Device API.

[`wake-lock`](feature-policy/wake-lock)

No

No

No

No

No

No

[`xr-spatial-tracking`](feature-policy/xr-spatial-tracking)

No

79

No

No

No

No

See also
--------

-   [Feature Policy](../feature_policy)
-   [Using Feature Policy](../feature_policy/using_feature_policy)
-   [`Document.featurePolicy`](https://developer.mozilla.org/en-US/docs/Web/API/Document/featurePolicy) and [`FeaturePolicy`](https://developer.mozilla.org/en-US/docs/Web/API/FeaturePolicy)
-   [Feature-Policy Tester (Chrome Developer Tools extension)](https://chrome.google.com/webstore/detail/feature-policy-tester-dev/pchamnkhkeokbpahnocjaeednpbpacop)
-   [`Content-Security-Policy`](content-security-policy)
-   [`Referrer-Policy`](referrer-policy)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Feature-Policy$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Feature-Policy" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Feature-Policy</a>
