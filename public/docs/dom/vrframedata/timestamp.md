VRFrameData.timestamp
=====================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `timestamp` read-only property of the [`VRFrameData`](../vrframedata) interface returns a constantly increasing timestamp value representing the time a frame update occurred.

Timestamps are useful for determining if position state data has been updated from the hardware. Since values are monotonically increasing, they can be compared to determine the ordering of updates — newer values will always be greater than or equal to older values.

The timestamp starts at 0 the first time [`VRDisplay.getFrameData()`](../vrdisplay/getframedata) is invoked for a given [`VRDisplay`](../vrdisplay).

Syntax
------

    var myTimestamp = vrFrameDataInstance.timestamp;

### Value

A [`DOMHighResTimeStamp`](../domhighrestimestamp) object.

Examples
--------

    var frameData = new VRFrameData();
    var vrDisplay;

    navigator.getVRDisplays().then(function(displays) {
      vrDisplay = displays[0];
      console.log('Display found');
      // Starting the presentation when the button is clicked: It can only be called in response to a user gesture
      btn.addEventListener('click', function() {
        vrDisplay.requestPresent([{ source: canvas }]).then(function() {
          drawVRScene();
        });
      });
    });

    // WebVR: Draw the scene for the WebVR display.
    function drawVRScene() {
      // WebVR: Request the next frame of the animation
      vrSceneFrame = vrDisplay.requestAnimationFrame(drawVRScene);

      // Populate frameData with the data of the next frame to display
      vrDisplay.getFrameData(frameData);

      // grab the current timestamp on each run of the rendering loop
      // and do something with it
      framedata.timestamp

        ...

      // WebVR: Indicates that we are ready to present the rendered frame to the VR display
      vrDisplay.submitFrame();
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webvr/spec/1.1/#dom-vrframedata-timestamp">WebVR 1.1<br />
<span class="small">The definition of 'timestamp' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`timestamp`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/VRFrameData/timestamp" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/VRFrameData/timestamp</a>
