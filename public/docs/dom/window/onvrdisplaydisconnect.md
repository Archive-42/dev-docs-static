Window.onvrdisplaydisconnect
============================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `onvrdisplaydisconnect` event handler property of the [`Window`](../window) interface is called when a compatible VR display has been disconnected from the computer (when the `vrdisplaydisconnect` event fires).

The event object is of type [`VRDisplayEvent`](../vrdisplayevent).

Syntax
------

    window.onvrdisplaydisconnect = function() { ... };

Examples
--------

    window.onvrdisplaydisconnect = function() {
      info.textContent = 'Display disconnected.';
    };

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webvr/spec/1.1/#dom-window-onvrdisplaydisconnect">WebVR 1.1<br />
<span class="small">The definition of 'onvrdisplaydisconnect' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`onvrdisplaydisconnect`

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

56

\["Chrome for Android 56 supports only Google Daydream View.", "Chrome for Android 57 adds support for Google Cardboard."\]

55

No

No

6.0

Supported on Samsung Internet for GearVR.

See also
--------

-   [WebVR API homepage](../webvr_api)
-   <https://mixedreality.mozilla.org/> — demos, downloads, and other resources from the Mozilla VR team.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Window/onvrdisplaydisconnect" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Window/onvrdisplaydisconnect</a>
