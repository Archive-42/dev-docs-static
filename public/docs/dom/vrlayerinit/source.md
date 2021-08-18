VRLayerInit.source
==================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `source` property of the [`VRLayerInit`](../vrlayerinit) interface (dictionary) defines the canvas whose contents will be presented by the [`VRDisplay`](../vrdisplay).

Syntax
------

    var myVRLayerInit = { };
    myVRLayerInit.source = myCanvas;

### Value

An [`HTMLCanvasElement`](../htmlcanvaselement) or [`OffscreenCanvas`](../offscreencanvas) object.

Examples
--------

    // currently returns an empty array
    var layers = vrDisplay.getLayers();

    if(navigator.getVRDisplays) {
      console.log('WebVR 1.1 supported');
      // Then get the displays attached to the computer
      navigator.getVRDisplays().then(function(displays) {
        // If a display is available, use it to present the scene
        if(displays.length > 0) {
          vrDisplay = displays[0];
          console.log('Display found');
          // Starting the presentation when the button is clicked: It can only be called in response to a user gesture
          btn.addEventListener('click', function() {
            vrDisplay.requestPresent([{ source: canvas }]).then(function() {
              console.log('Presenting to WebVR display');

              // Here it returns an array of VRLayerInit objects
              var layers = vrDisplay.getLayers();

              ...
            });
          });
        }
      });
    }

[`VRLayerInit`](../vrlayerinit) objects look something like this:

    {
      leftBounds : [ ... ],
      rightBounds: [ ... ],
      source: canvasReference
    }

**Note**: The `canvasReference` refers to the [`<canvas>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/canvas) element itself, not the WebGL context associated with the canvas. The other two members are arrays

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webvr/spec/1.1/#dom-vrlayerinit-source">WebVR 1.1<br />
<span class="small">The definition of 'source' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`source`

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

-   [WebVR API homepage](../webvr_api)
-   <https://mixedreality.mozilla.org/> — demos, downloads, and other resources from the Mozilla VR team.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/VRLayerInit/source" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/VRLayerInit/source</a>
