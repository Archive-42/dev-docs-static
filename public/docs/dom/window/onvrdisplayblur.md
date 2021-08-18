Window.onvrdisplayblur
======================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `onvrdisplayblur` property of the [`Window`](../window) interface represents an event handler that will run when presentation to a display has been paused for some reason by the browser, OS, or VR hardware (when the `vrdisplayblur` event fires) — for example, while the user is interacting with a system menu or browser, to prevent tracking or loss of experience.

While a [`VRDisplay`](../vrdisplay) is blurred it does not lose it’s presenting status ([`VRDisplay.isPresenting`](../vrdisplay/ispresenting) continues to report `true`) but [`VRDisplay.getFrameData()`](../vrdisplay/getframedata) returns `false` without updating the provided [`VRFrameData`](../vrframedata) and [`VRDisplay.getPose()`](../vrdisplay/getpose) returns a [`VRPose`](../vrpose) with `null` members.

The event object is of type [`VRDisplayEvent`](../vrdisplayevent).

Syntax
------

    window.onvrdisplayblur = function() { ... };

Examples
--------

    window.onvrdisplayblur = function() {
      info.textContent = 'Display unfocused.';
    };

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webvr/spec/1.1/#dom-window-onvrdisplayblur">WebVR 1.1<br />
<span class="small">The definition of 'onvrdisplayblur' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`onvrdisplayblur`

No

15-79

No

No

No

No

No

No

No

No

No

No

See also
--------

-   [WebVR API homepage](../webvr_api)
-   <https://mixedreality.mozilla.org/> — demos, downloads, and other resources from the Mozilla VR team.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Window/onvrdisplayblur" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Window/onvrdisplayblur</a>
