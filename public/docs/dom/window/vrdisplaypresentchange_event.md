Window: vrdisplaypresentchange event
====================================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `vrdisplaypresentchange` event of the [WebVR API](../webvr_api) is fired when the presenting state of a VR display changes — i.e. goes from presenting to not presenting, or vice versa.

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../vrdisplayevent"><code>VRDisplayEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td><code>onvrdisplaypresentchange</code></td></tr></tbody></table>

Examples
--------

You can use the `vrdisplaypresentchange` event in an `addEventListener` method:

    window.addEventListener('vrdisplaypresentchange', function() {
      if(vrDisplay.isPresenting) {
        info.textContent = 'Display has started presenting.';
      } else {
        info.textContent = 'Display has stopped presenting.';
      }
      reportDisplays();
    });

Or use the `onvrdisplaypresentchange` event handler property:

    window.onvrdisplaypresentchange = function() {
      if(vrDisplay.isPresenting) {
        info.textContent = 'Display has started presenting.';
      } else {
        info.textContent = 'Display has stopped presenting.';
      }
      reportDisplays();
    };

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webvr/spec/1.1/#dom-window-onvrdisplaypresentchange">WebVR 1.1<br />
<span class="small">The definition of 'vrdisplaypresentchange' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`vrdisplaypresentchange_event`

65

15

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Window/vrdisplaypresentchange_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Window/vrdisplaypresentchange_event</a>
