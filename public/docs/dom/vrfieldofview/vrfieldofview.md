VRFieldOfView.VRFieldOfView()
=============================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `VRFieldOfView()` constructor creates a new [`VRFieldOFView`](../vrfieldofview) object.

Syntax
------

There are two forms of this constructor, which take their information in slightly different ways. The first one accepts four separate arguments — the [`VRFieldOfView.upDegrees`](updegrees), [`VRFieldOfView.rightDegrees`](rightdegrees), [`VRFieldOfView.downDegrees`](downdegrees), and [`VRFieldOfView.leftDegrees`](leftdegrees) values you want the field of view to have

    var myFOV = new VRFieldOfView(upDegrees, rightDegrees, downDegrees, leftDegrees);

The second one takes a `VRFieldOfViewInit` object as a single argument, which is just a dictionary containing the four degree values mentioned above:

    var init = {upDegrees:up,rightDegrees:right,downDegrees:down,leftDegrees:left}
    var myFOV = new VRFieldOfView(init);

### Parameters

-   Four argument version:

    upDegrees  
    The number of degrees upwards that the field of view will extend in.

    rightDegrees  
    The number of degrees to the right that the field of view will extend in.

    downDegrees  
    The number of degrees downwards that the field of view will extend in.

    leftDegrees  
    The number of degrees to the left that the field of view will extend in.

-   One argument version:

    init  
    A dictionary object containing the four degree values specified above.

Examples
--------

The following simple example shows a function that can be used to set a custom field of view with four specified degree values for up, right, down and left. The `VRFieldOfView()` constructor is used to create a [`VRFieldOfView`](../vrfieldofview) object from the supplied values, which is then fed into the [`HMDVRDevice.setFieldOfView`](../hmdvrdevice/setfieldofview) method.

    function setCustomFOV(up,right,down,left) {
      var testFOV = new VRFieldOfView(up,right,down,left);

      gHMD.setFieldOfView(testFOV,testFOV,0.01,10000.0);

      var lEye = gHMD.getEyeParameters('left');
      var rEye = gHMD.getEyeParameters('right');
      console.log(lEye.currentFieldOfView);
      console.log(rEye.currentFieldOfView);
    }

**Note**: When testing, setting a weird/tiny field of view can really mess up your view. It is a good idea to grab the current field of view first (using [`VREyeParameters.fieldOfView`](../vreyeparameters/fieldofview)) before making any drastic changes, so you can reset it afterwards if needed.

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

`VRFieldOfView`

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
-   <https://mixedreality.mozilla.org/> — demos, downloads, and other resources from the Mozilla VR team.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/VRFieldOfView/VRFieldOfView" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/VRFieldOfView/VRFieldOfView</a>
