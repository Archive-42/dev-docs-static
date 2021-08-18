VRDisplay.isConnected
=====================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `isConnected` read-only property of the [`VRDisplay`](../vrdisplay) interface returns a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) indicating whether the `VRDisplay` is connected to the computer.

Syntax
------

    var isItConnected = vrDisplayInstance.isConnected;

### Value

A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean); `true` means the display is connected; `false` means it isn't.

Examples
--------

    navigator.getVRDisplays().then(function(displays) {
      // If a display is available, use it to present the scene
      if(displays.length > 0) {
        vrDisplay = displays[0];

        // Starting the presentation when the button is clicked: It can only be called in response to a user gesture
        btn.addEventListener('click', function() {
          // Only request presentation if the display is still connected.
          if(vrDisplay.isConnected) {
            vrDisplay.requestPresent([{ source: canvas }]).then(function() {
              // start rendering the app, etc.
            });
          } else {
            console.log('Connection to display lost');
          }
        });
      }
    });  

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webvr/spec/1.1/#dom-vrdisplay-isconnected">WebVR 1.1<br />
<span class="small">The definition of 'isConnected' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`isConnected`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/VRDisplay/isConnected" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/VRDisplay/isConnected</a>
