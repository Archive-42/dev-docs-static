VRDisplayCapabilities.hasExternalDisplay
========================================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `hasExternalDisplay` read-only property of the [`VRDisplayCapabilities`](../vrdisplaycapabilities) interface returns a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) stating whether the VR display is separate from the device's primary display.

**Note**: If presenting VR content would obscure other content on the device, this will return `false`, in which case the application should not attempt to mirror VR content or update non-VR UI because that content will not be visible.

Syntax
------

    var hasAnExternalDisplay = vrDisplayCapabilitiesInstance.hasExternalDisplay;

### Value

A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean).

Examples
--------

    function reportDisplays() {
      navigator.getVRDisplays().then(function(displays) {
        for(var i = 0; i < displays.length; i++) {
          var cap = displays[i].capabilities;
          // cap is a VRDisplayCapabilities object
          var listItem = document.createElement('li');
          listItem.innerHTML = '<strong>Display ' + (i+1) + '</strong>'
                       + '<br>VR Display ID: ' + displays[i].displayId
                       + '<br>VR Display Name: ' + displays[i].displayName
                       + '<br>Display can present content: ' + cap.canPresent
                       + '<br>Display is separate from the computer\'s main display: ' + cap.hasExternalDisplay
                       + '<br>Display can return position info: ' + cap.hasPosition
                       + '<br>Display can return orientation info: ' + cap.hasOrientation
                       + '<br>Display max layers: ' + cap.maxLayers;
          list.appendChild(listItem);
        }
      });
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webvr/spec/1.1/#dom-vrdisplaycapabilities-hasexternaldisplay">WebVR 1.1<br />
<span class="small">The definition of 'hasExternalDisplay' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`hasExternalDisplay`

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

No

6.0

Google Cardboard supported in Samsung Internet 7.0.

See also
--------

-   [WebVR API homepage](../webvr_api)
-   <https://mixedreality.mozilla.org/> — demos, downloads, and other resources from the Mozilla VR team.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/VRDisplayCapabilities/hasExternalDisplay" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/VRDisplayCapabilities/hasExternalDisplay</a>
