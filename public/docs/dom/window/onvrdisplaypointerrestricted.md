Window.onvrdisplaypointerrestricted
===================================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `onvrdisplaypointerrestricted` property of the [`Window`](../window) interface represents an event handler that will run when the VR display's pointer input is restricted to consumption via a [pointerlocked element](../pointer_lock_api).

The event object is of type [`VRDisplayEvent`](../vrdisplayevent).

Syntax
------

    window.onvrdisplaypointerrestricted = functionRef;

Examples
--------

    window.onvrdisplaypointerrestricted = function() {
      // Run code to handle pointer lock
    };

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webvr/spec/1.1/#dom-window-onvrdisplaypointerrestricted">WebVR 1.1<br />
<span class="small">The definition of 'onvrdisplaypointerrestricted' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`onvrdisplaypointerrestricted`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Window/onvrdisplaypointerrestricted" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Window/onvrdisplaypointerrestricted</a>
