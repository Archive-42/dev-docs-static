# Navigator.activeVRDisplays

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `activeVRDisplays` read-only property of the [`Navigator`](../navigator) interface returns an array containing every [`VRDisplay`](../vrdisplay) object that is currently presenting ([`VRDisplay.ispresenting`](../vrdisplay/ispresenting) is `true`).

## Syntax

    var myActiveDisplays = navigator.activeVRDisplays;

### Value

An array of [`VRDisplay`](../vrdisplay) objects.

## Examples

    function showActive() {
      var displays = navigator.activeVRDisplays;
      for(var i = 0; i < displays.length; i++) {
        console.log('Display ' + displays[i].displayId + ' is active.');
      }
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webvr/spec/1.1/#navigator-activevrdisplays-attribute">WebVR 1.1<br />
<span class="small">The definition of 'activeVRDisplays' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`activeVRDisplays`

No

15-79

WebVR content requires a Windows Mixed Reality headset or the Windows Mixed Reality Portal Simulator.

55

Windows support was enabled in Firefox 55.

64

macOS support was enabled in Firefox 64.

No

No

No

No

79-80

Supported only by Google Daydream.

55

No

No

12.0-13.0

Supported only by Google Daydream.

`secure_context_required`

No

No

73

No

No

No

79-80

79-80

No

No

No

12.0-13.0

## See also

- [WebVR API homepage](../webvr_api)
- <https://mixedreality.mozilla.org/> — demos, downloads, and other resources from the Mozilla VR team.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Navigator/activeVRDisplays" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Navigator/activeVRDisplays</a>
