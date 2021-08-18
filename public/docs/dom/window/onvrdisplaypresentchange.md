Window.onvrdisplaypresentchange
===============================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `onvrdisplaypresentchange` property of the [`Window`](../window) interface represents an event handler that will run when the presenting state of a VR display changes — i.e. goes from presenting to not presenting, or vice versa (when the `vrdisplaypresentchange` event fires).

The event object is of type [`VRDisplayEvent`](../vrdisplayevent).

Syntax
------

    window.onvrdisplaypresentchange = functionRef;

Examples
--------

The presenting state of a [`VRDisplay`](../vrdisplay) can be checked using the [`VRDisplay.isPresenting`](../vrdisplay/ispresenting) property.

    window.onvrdisplaypresentchange = function() {
      if(vrDisplay.isPresenting) {
        info.textContent = 'Display has started presenting.';
      } else {
        info.textContent = 'Display has stopped presenting.';
      }
    };

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webvr/spec/1.1/#dom-window-onvrdisplaypresentchange">WebVR 1.1<br />
<span class="small">The definition of 'onvrdisplaypresentchange' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`onvrdisplaypresentchange`

65-80

15

55

Windows support was enabled in Firefox 55.

64

macOS support was enabled in Firefox 64.

No

No

No

No

56-80

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Window/onvrdisplaypresentchange" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Window/onvrdisplaypresentchange</a>
