XREnvironmentBlendMode
======================

The WebXR API's enumerated type `XREnvironmentBlendMode` defines strings used to identify if and how to blend the rendered virtual content with the real world. Its values are used by the [`XRSession`](xrsession) interface's [`environmentBlendMode`](xrsession/environmentblendmode) property.

Values
------

`opaque`  
The rendered image is drawn without allowing any pass-through imagery. This is primarily used by fully-immersive VR headsets, which totally obscure the surrounding environment, with none of the real world shown to the user at all. The alpha values specified in the [`XRSession`](xrsession)'s [`renderState`](xrsession/renderstate) property's `baseLayer` field are ignored since the alpha values for the rendered imagery are all treated as being 1.0 (fully opaque).

`additive`  
Primarily used by AR devices with transparent lenses which directly allow reality to pass through to the user's eyes, the `additive` blending mode is designed to be used in a situation in which the device has no control over the background and its brightness, since that isn't being digitally controlled. All the device can do is add more light to the image; it can't make things get darker. Therefore, black is rendered as fully transparent, and there's no way to make a pixel fully opaque. As with the `opaque` setting, alpha values specified are ignored and treated as if they were 1.0.

`alpha-blend`  
Used by headsets or goggles which use cameras to capture the real world and display it digitally on the screen or screens used to render the content for the user to see, this offers a way to create an AR presentation using a VR device. Alpha blending can also be used by non-wearable devices that provide AR modes, such as phones or tablets using cameras to capture the real world for use in AR apps. Since the real world is being digitally presented, the brightness of each pixel can be controlled, whether it's reality or the rendered XR image, the user's environment can be blended with the virtual environment with each pixel having its color and brightness precisely controlled.

In this mode, the `XRSession`'s `renderState.baseLayer` property provides relative weights of the artificial layer during the compositing process. Pixels whose alpha value is 1.0 are rendered fully opaque, totally obscuring the real world, while pixels with an alpha of 1.0 are totally transparent, leaving the surrounding environment to pass through.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webxr-ar-module/#xrenvironmentblendmode-enum">WebXR Augmented Reality Module<br />
<span class="small">The definition of 'XREnvironmentBlendMode' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`XREnvironmentBlendMode`

79

79

No

No

No

No

79

79

No

No

No

11.2

`additive`

79

79

No

No

No

No

79

79

No

No

No

11.2

`alpha-blend`

79

79

No

No

No

No

79

79

No

No

No

11.2

`opaque`

79

79

No

No

No

No

79

79

No

No

No

11.2

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XREnvironmentBlendMode" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XREnvironmentBlendMode</a>
