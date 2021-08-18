VRFieldOfView
=============

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `VRFieldOfView` interface of the [WebVR API](webvr_api) represents a field of view defined by 4 different degree values describing the view from a center point.

Properties
----------

 [`VRFieldOfView.upDegrees`](vrfieldofview/updegrees) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span> <span class="badge inline readonly">Read only </span>   
The number of degrees upwards that the field of view extends in.

 [`VRFieldOfView.rightDegrees`](vrfieldofview/rightdegrees) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span> <span class="badge inline readonly">Read only </span>   
The number of degrees to the right that the field of view extends in.

 [`VRFieldOfView.downDegrees`](vrfieldofview/downdegrees) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span> <span class="badge inline readonly">Read only </span>   
The number of degrees downwards that the field of view extends in.

 [`VRFieldOfView.leftDegrees`](vrfieldofview/leftdegrees) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span> <span class="badge inline readonly">Read only </span>   
The number of degrees to the left that the field of view extends in.

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

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webvr/spec/1.1/#interface-interface-vrfieldofview">WebVR 1.1<br />
<span class="small">The definition of 'VRFieldOfView' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`downDegrees`

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

`leftDegrees`

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

`rightDegrees`

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

`upDegrees`

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

-   [WebVR API homepage](webvr_api)
-   <https://mixedreality.mozilla.org/> — demos, downloads, and other resources from the Mozilla VR team.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/VRFieldOfView" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/VRFieldOfView</a>
