Window.onvrdisplayconnect
=========================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `onvrdisplayconnect` property of the [`Window`](../window) interface represents an event handler that will run when a compatible VR display has been connected to the computer (when the `vrdisplayconnect` event fires).

The event object is of type [`VRDisplayEvent`](../vrdisplayevent).

Syntax
------

    window.onvrdisplayconnect = function() { ... };

Examples
--------

    window.onvrdisplayconnect = function() {
      info.textContent = 'Display connected.';
    };

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webvr/spec/1.1/#dom-window-onvrdisplayconnect">WebVR 1.1<br />
<span class="small">The definition of 'onvrdisplayconnect' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`onvrdisplayconnect`

No

15-79

55

Windows support was enabled in Firefox 55.

64

macOS support was enabled in Firefox 64.

No

No

No

No

Yes

\["Chrome for Android 56 supports only Google Daydream View.", "Chrome for Android 57 adds support for Google Cardboard."\]

55

No

No

Yes

Supported on Samsung Internet for GearVR.

See also
--------

-   [WebVR API homepage](../webvr_api)
-   <https://mixedreality.mozilla.org/> — demos, downloads, and other resources from the Mozilla VR team.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Window/onvrdisplayconnect" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Window/onvrdisplayconnect</a>
