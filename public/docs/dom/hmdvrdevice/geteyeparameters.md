HMDVRDevice.getEyeParameters()
==============================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `getEyeParameters()` method of the [`HMDVRDevice`](../hmdvrdevice) interface returns current parameters for the eye specified as its argument ("left" or "right") — stored in a [`VREyeParameters`](../vreyeparameters) object.

This includes field of view information, and more.

Syntax
------

    var myLeftEye = HMDVRDevice.getEyeParameters('left');

### Parameters

`whichEye`  
A [`DOMString`](../domstring) representing the eye you want to return information about. The value can be `left` or `right`.

### Returns

A [`VREyeParameters`](../vreyeparameters) object.

Examples
--------

The following example is taken from the Mozilla VR Team's [threejs-vr-boilerplate](https://github.com/MozVR/vr-web-examples/tree/master/threejs-vr-boilerplate) code — to be precise, the [VREffect.js file](https://github.com/MozVR/vr-web-examples/blob/master/threejs-vr-boilerplate/js/VREffect.js#L28-L29). Early on in the code the `getEyeParameters()` method is used to access information about each eye, which is then used for rendering calculations later on.

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

`getEyeParameters`

No

No

39

The support for this feature is currently disabled by default in Firefox. To enable WebVR support in Firefox Nightly/Developer Edition, you can go to `about:config` and enable the `dom.vr*` prefs. A better option however is to install the [WebVR Enabler Add-on](http://www.mozvr.com/downloads/webvr-addon-0.1.0.xpi), which does this for you and sets up other necessary parts of the [environment](https://developer.mozilla.org/docs/Web/API/WebVR_API/WebVR_environment_setup)

No

No

No

No

62

The support in Chrome is currently experimental. To find information on Chrome's WebVR implementation status including supporting builds, check out [Bringing VR to Chrome](http://blog.tojicode.com/2014/07/bringing-vr-to-chrome.html) by Brandon Jones.

44

The `dom.vr*` prefs are enabled by default at this point, in Nightly/Aurora editions.

39-44

The support for this feature is currently disabled by default in Firefox. To enable WebVR support in Firefox Nightly/Developer Edition, you can go to `about:config` and enable the `dom.vr*` prefs. A better option however is to install the [WebVR Enabler Add-on](http://www.mozvr.com/downloads/webvr-addon-0.1.0.xpi), which does this for you and sets up other necessary parts of the [environment](https://developer.mozilla.org/docs/Web/API/WebVR_API/WebVR_environment_setup).

No

No

8.0

See also
--------

-   [WebVR API homepage](../webvr_api).
-   <https://mixedreality.mozilla.org/> — demos, downloads, and other resources from the Mozilla VR team.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HMDVRDevice/getEyeParameters" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HMDVRDevice/getEyeParameters</a>
