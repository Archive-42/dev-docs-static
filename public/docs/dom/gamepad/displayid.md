# Gamepad.displayId

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `displayId` read-only property of the [`Gamepad`](../gamepad) interface returns the [`VRDisplay.displayId`](../vrdisplay/displayid) of the associated [`VRDisplay`](../vrdisplay) — the `VRDisplay` that the gamepad is controlling the displayed scene of.

A Gamepad is considered to be associated with a [`VRDisplay`](../vrdisplay) if it reports a pose that is in the same space as the <span class="page-not-created">`VRDisplay.pose`</span>.

## Syntax

    var myDisplayId = gamepadInstance.displayId;

### Value

A number representing the associated [`VRDisplay.displayId`](../vrdisplay/displayid). If the number is 0, then the gamepad is not associated with a VR display.

## Examples

    window.addEventListener("gamepadconnected", function(e) {
      if(!e.gamepad.displayId) {
        console.log('Gamepad connected');
      } else {
        console.log('Gamepad connected, associated with VR display ' + e.gamepad.displayId);
      }
    });

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webvr/spec/1.1/#gamepad-getvrdisplays-attribute">WebVR 1.1<br />
<span class="small">The definition of 'displayId' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition</td></tr></tbody></table>

## Browser compatibility

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

`displayId`

55-80

Only works on desktop in an [experimental version of Chrome](https://webvr.info/get-chrome/) (other builds won't return any devices when `Navigator.getVRDisplays()` is invoked).

79-80

15-79

55

Windows support was enabled in Firefox 55.

64

macOS support was enabled in Firefox 64.

No

No

No

No

55-80

Currently supported only by Google Daydream.

55

?

No

6.0-13.0

Currently supported only by Google Daydream.

## See also

- [WebVR API homepage](../webvr_api)
- <https://mixedreality.mozilla.org/> — demos, downloads, and other resources from the Mozilla VR team.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Gamepad/displayId" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Gamepad/displayId</a>
