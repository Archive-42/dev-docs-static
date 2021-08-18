VRDisplayEvent.reason
=====================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `reason` read-only property of the [`VRDisplayEvent`](../vrdisplayevent) interface returns a human-readable reason why the event was fired.

Syntax
------

    var myReason = vrDisplayEventInstance.reason;

### Value

A string representing the reason why the event was fired. The available reasons are defined in the `VRDisplayEventReason` enum, and are as follows:

-   `mounted` — The [`VRDisplay`](../vrdisplay) has detected that the user has put it on (or it has been otherwise activated).
-   `navigation` — The page has been navigated to from a context that allows this page to begin presenting immediately, such as from another site that was already in VR presentation mode.
-   `requested` — The user agent has requested that VR presentation mode be started. This allows user agents to include a consistent UI to enter VR across different sites.
-   `unmounted` — The [`VRDisplay`](../vrdisplay) has detected that the user has taken it off (or it has been otherwise slept/put on standby).

Examples
--------

    window.addEventListener('vrdisplaypresentchange', function(e) {
      console.log('Display ' + e.display.displayId + ' presentation has changed. Reason given: ' + e.reason + '.');
    })

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webvr/spec/1.1/#dom-vrdisplayeventinit-reason">WebVR 1.1<br />
<span class="small">The definition of 'reason' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`reason`

No

15-79

55

Windows support was enabled in Firefox 55.

64

macOS support was enabled in Firefox 64.

No

?

No

No

56-80

\["Only works in an [experimental version of Chrome](https://webvr.info/get-chrome/). (Other builds won't return any devices when `Navigator.getVRDisplays()` is invoked.)", "Daydream View supported in Chrome 56.", "Google Cardboard supported in Chrome 57."\]

55

?

?

6.0

Google Cardboard supported in Samsung Internet 7.0.

See also
--------

-   [WebVR API homepage](../webvr_api)
-   <https://mixedreality.mozilla.org/> — demos, downloads, and other resources from the Mozilla VR team.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/VRDisplayEvent/reason" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/VRDisplayEvent/reason</a>
