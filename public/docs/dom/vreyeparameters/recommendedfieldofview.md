VREyeParameters.recommendedFieldOfView
======================================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `recommendedFieldOfView` read-only property of the [`VREyeParameters`](../vreyeparameters) interface describes the recommended field of view for the current eye — ideally based on user calibration.

Syntax
------

    var recFOV = myEyeParameters.recommendedFieldOfView;

### Value

A [`VRFieldOfView`](../vrfieldofview) object.

Examples
--------

The following example is taken from the Mozilla VR Team's [threejs-vr-boilerplate](https://github.com/MozVR/vr-web-examples/tree/master/threejs-vr-boilerplate) code — to be precise, the [VREffect.js file](https://github.com/MozVR/vr-web-examples/blob/master/threejs-vr-boilerplate/js/VREffect.js#L28-L29). Early on in the code the [`HMDVRDevice.getEyeParameters`](../hmdvrdevice/geteyeparameters) method is used to access information about each eye — [`VREyeParameters.offset`](offset) and [`VREyeParameters.recommendedFieldOfView`](recommendedfieldofview) — which are used for rendering calculations later on.

    if ( vrHMD.getEyeParameters !== undefined ) {

        var eyeParamsL = vrHMD.getEyeParameters( 'left' );
        var eyeParamsR = vrHMD.getEyeParameters( 'right' );

        eyeTranslationL = eyeParamsL.eyeTranslation;
        eyeTranslationR = eyeParamsR.eyeTranslation;
        eyeFOVL = eyeParamsL.recommendedFieldOfView;
        eyeFOVR = eyeParamsR.recommendedFieldOfView;

    } else {

      ...

    }

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

`recommendedFieldOfView`

No

No

No

No

?

No

No

No

?

?

?

No

See also
--------

-   [WebVR API homepage](../webvr_api).
-   [`VRFieldOfView`](../vrfieldofview)
-   <https://mixedreality.mozilla.org/> — demos, downloads, and other resources from the Mozilla VR team.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/VREyeParameters/recommendedFieldOfView" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/VREyeParameters/recommendedFieldOfView</a>
