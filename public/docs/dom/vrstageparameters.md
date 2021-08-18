VRStageParameters
=================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `VRStageParameters` interface of the [WebVR API](webvr_api) represents the values describing the stage area for devices that support room-scale experiences.

This interface is accessible through the [`VRDisplay.stageParameters`](vrdisplay/stageparameters) property.

Properties
----------

 [`VRStageParameters.sittingToStandingTransform`](vrstageparameters/sittingtostandingtransform) <span class="badge inline readonly">Read only </span>   
Contains a matrix that transforms the sitting-space view matrices of [`VRFrameData`](vrframedata) to standing-space.

 [`VRStageParameters.sizeX`](vrstageparameters/sizex) <span class="badge inline readonly">Read only </span>   
Returns the width of the play-area bounds in meters.

 [`VRStageParameters.sizeY`](vrstageparameters/sizey) <span class="badge inline readonly">Read only </span>   
Returns the depth of the play-area bounds in meters.

Examples
--------

    var info = document.querySelector('p');
    var vrDisplay;

    navigator.getVRDisplays().then(function(displays) {
      vrDisplay = displays[0];
      var stageParams = vrDisplay.stageParameters;
      // stageParams is a VRStageParameters object

      if(stageParams === null) {
        info.textContent = 'Your VR Hardware does not support room-scale experiences.'
      } else {
        info.innerHTML = '<strong>Display stage parameters</strong>'
                     + '<br>Sitting to standing transform: ' + stageParams.sittingToStandingTransform
                     + '<br>Play area width (m): ' + stageParams.sizeX
                     + '<br>Play area depth (m): ' + stageParams.sizeY
      }
    });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webvr/spec/1.1/#interface-vrstageparameters">WebVR 1.1<br />
<span class="small">The definition of 'VRStageParameters' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`VRStageParameters`

No

≤18-79

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

`sittingToStandingTransform`

No

≤18-79

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

`sizeX`

No

≤18-79

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

`sizeY`

No

≤18-79

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

-   [WebVR API homepage](webvr_api)
-   <https://mixedreality.mozilla.org/> — demos, downloads, and other resources from the Mozilla VR team.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/VRStageParameters" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/VRStageParameters</a>
