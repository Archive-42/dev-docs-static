VRDevice.resetPose()
====================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `resetPose()` method of the [`VRDisplay`](../vrdisplay) interface resets the pose for the `VRDisplay`, treating its current [`VRPose.position`](../vrpose/position) and [`VRPose.orientation`](../vrpose/orientation) as the "origin/zero" values.

After `resetPost()` has been called, future poses returned from [`VRDisplay.getPose()`](getpose)/[`VRDisplay.getImmediatePose()`](getimmediatepose) will describe positions relative to the `VRDisplay`'s position when `resetPose()` was last called and will treat the display’s yaw when `resetPose()` was last called as the forward orientation.

The VRDisplay's reported roll and pitch do not change when `resetPose()` is called as they are relative to gravity. Calling `resetPose()` may change the [`VRStageParameters.sittingToStandingTransform`](../vrstageparameters/sittingtostandingtransform) matrix.

Syntax
------

    vrDisplayInstance.resetPose();

### Parameters

None.

### Return value

Void.

Examples
--------

    // Assuming vrDisplay already contains a VRDisplay object,
    // and we have a <button> referenced inside btn
    btn.addEventListener('click', function() {
      vrDisplay.resetPose();
      console.log('Current pose set as origin/center');
    });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webvr/spec/1.1/#dom-vrdisplay-resetpose">WebVR 1.1<br />
<span class="small">The definition of 'resetPose()' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`resetPose`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/VRDisplay/resetPose" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/VRDisplay/resetPose</a>
