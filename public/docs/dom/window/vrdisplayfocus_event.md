Window: vrdisplayfocus event
============================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `vrdisplayfocus` event of the [WebVR API](../webvr_api) is fired when presentation to a VR display has resumed after being blurred.

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../vrdisplayevent"><code>VRDisplayEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td><code>onvrdisplayfocus</code></td></tr></tbody></table>

Examples
--------

You can use the `vrdisplayfocus` event in an `addEventListener` method:

    window.addEventListener('vrdisplayfocus', function() {
      info.textContent = 'Display focused.';
      reportDisplays();
    });

Or use the `onvrdisplayfocus` event handler property:

    window.onvrdisplayfocus = function() {
      info.textContent = 'Display focused.';
      reportDisplays();
    };

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webvr/spec/1.1/#dom-window-onvrdisplayfocus">WebVR 1.1<br />
<span class="small">The definition of 'vrdisplayfocus' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`vrdisplayfocus_event`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Window/vrdisplayfocus_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Window/vrdisplayfocus_event</a>
