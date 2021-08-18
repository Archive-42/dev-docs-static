VRDisplay.getPose()
===================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `getPose()` method of the [`VRDisplay`](../vrdisplay) interface returns a [`VRPose`](../vrpose) object defining the future predicted pose of the `VRDisplay` as it will be when the current frame is actually presented.

This method is deprecated — instead, you should use [`VRDisplay.getFrameData()`](getframedata), which also provides a [`VRPose`](../vrpose) object.

Syntax
------

    var myPose = vrDisplayInstance.getPose();

### Parameters

None.

### Return value

A [`VRPose`](../vrpose) object.

Examples
--------

Once we have a reference to a [`VRDisplay`](../vrdisplay) object, we can retrieve the [`VRPose`](../vrpose) representing the current pose of the display.

    if(navigator.getVRDisplays) {
      console.log('WebVR 1.1 supported');
      // Then get the displays attached to the computer
      navigator.getVRDisplays().then(function(displays) {
        // If a display is available, use it to present the scene
        if(displays.length > 0) {
          vrDisplay = displays[0];
          console.log('Display found');

              // Return the current VRPose object for the display
              var pose = vrDisplay.getPose();

              ...

        }
      });
    }

It is however recommended that you use the non-deprecated [`pose`](../vrframedata/pose) property of the [`VRFrameData`](../vrframedata) object (retrieved via [`VRDisplay.getFrameData()`](getframedata)) to retrieve the current pose for each frame before it is submitted to the display to be presented. This happens on each iteration of the rendering loop for your app, so you can be sure the pose data is current.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webvr/spec/1.1/#dom-vrdisplay-getpose">WebVR 1.1<br />
<span class="small">The definition of 'getPose()' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`getPose`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/VRDisplay/getPose" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/VRDisplay/getPose</a>
