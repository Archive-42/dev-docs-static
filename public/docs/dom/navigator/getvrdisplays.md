Navigator.getVRDisplays()
=========================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `getVRDisplays()` method of the [`Navigator`](../navigator) interface returns a promise that resolves to an array of [`VRDisplay`](../vrdisplay) objects representing any available VR displays connected to the computer.

Syntax
------

    navigator.getVRDisplays().then(function(displays) {
      // Do something with the available VR displays
    });

### Parameters

None.

### Return value

A promise that resolves to an array of [`VRDisplay`](../vrdisplay) objects.

Examples
--------

    if(navigator.getVRDisplays) {
      console.log('WebVR 1.1 supported');
      // Then get the displays attached to the computer
      navigator.getVRDisplays().then(function(displays) {
        // If a display is available, use it to present the scene
        if(displays.length > 0) {
          vrDisplay = displays[0];
          // Now we have our VRDisplay object and can do what we want with it
        }
      });
    }

**Note**: You can see this complete code at [raw-webgl-example](https://github.com/mdn/webvr-tests/blob/master/raw-webgl-example/webgl-demo.js).

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webvr/spec/1.1/#navigator-getvrdisplays-attribute">WebVR 1.1<br />
<span class="small">The definition of 'getVRDisplays()' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`getVRDisplays`

No

Available on all platforms behind a flag, but currently only works on desktop in an [experimental version of Chrome](https://webvr.info/get-chrome/) (other builds won't return any devices when `Navigator.getVRDisplays()` is invoked).

15-79

55

Windows support was enabled in Firefox 55.

64

macOS support was enabled in Firefox 64.

No

No

No

No

Yes-80

Currently supported only by Google Daydream.

55

No

No

Yes-13.0

Currently supported only by Google Daydream.

See also
--------

-   [WebVR API homepage](../webvr_api)
-   <https://mixedreality.mozilla.org/> — demos, downloads, and other resources from the Mozilla VR team.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Navigator/getVRDisplays" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Navigator/getVRDisplays</a>
