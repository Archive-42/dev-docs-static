VREyeParameters.offset
======================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `offset` read-only property of the [`VREyeParameters`](../vreyeparameters) interface represents the offset from the center point between the user's eyes to the center of the eye, measured in meters.

This value should represent half the user’s interpupillary distance (IPD), but may also represent the distance from the center point of the headset to the center point of the lens for the given eye.

Syntax
------

    var myOffset = eyeParametersInstance.offset;

### Value

A [`Float32Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Float32Array) representing a vector describing the offset from the center point between the users eyes to the center of the eye in meters.

**Note**: Values for the left eye will be negative; values for the right eye will be positive.

Examples
--------

    var info = document.querySelector('p');
    var list = document.querySelector('ul');
    var vrDisplay;

    if(navigator.getVRDisplays) {
        reportFieldOfView();
    } else {
      info.textContent = 'WebVR API not supported by this browser.'
    }

    function reportFieldOfView() {
      navigator.getVRDisplays().then(function(displays) {
        vrDisplay = displays[0];
        var lEye = vrDisplay.getEyeParameters('left');
        var rEye = vrDisplay.getEyeParameters('right');
        // lEye and rEye are VREyeParameters objects

        var lFOV = lEye.fieldOfView;
        var rFOV = rEye.fieldOfView;
        // lFOV and rFOV are VRFieldOfView objects

        var listitem1 = document.createElement('li');
        var listitem2 = document.createElement('li');

        listitem1.innerHTML = '<strong>Left eye parameters</strong>'
                     + '<br>Offset: ' + lEye.offset
                     + '<br>Render width: ' + lEye.renderWidth
                     + '<br>Render height: ' + lEye.renderHeight
                     + '<br>Up degrees: ' + lFOV.upDegrees
                     + '<br>Right degrees: ' + lFOV.rightDegrees
                     + '<br>Down degrees: ' + lFOV.downDegrees
                     + '<br>Left degrees: ' + lFOV.leftDegrees

       listitem2.innerHTML = '<strong>Right eye parameters</strong>'
                    + '<br>Offset: ' + rEye.offset
                    + '<br>Render width: ' + rEye.renderWidth
                    + '<br>Render height: ' + rEye.renderHeight
                    + '<br>Up degrees: ' + rFOV.upDegrees
                    + '<br>Right degrees: ' + rFOV.rightDegrees
                    + '<br>Down degrees: ' + rFOV.downDegrees
                    + '<br>Left degrees: ' + rFOV.leftDegrees

        list.appendChild(listitem1);
        list.appendChild(listitem2);
      });
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webvr/spec/1.1/#dom-vreyeparameters-offset">WebVR 1.1<br />
<span class="small">The definition of 'offset' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`offset`

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

-   [WebVR API homepage](../webvr_api).
-   <https://mixedreality.mozilla.org/> — demos, downloads, and other resources from the Mozilla VR team.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/VREyeParameters/offset" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/VREyeParameters/offset</a>
