XRWebGLLayerInit.antialias
==========================

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The Boolean `antialias` property, if present and set to `true` in the [`XRWebGLLayerInit`](../xrwebgllayerinit) object provided as the [`XRWebGLLayer()`](../xrwebgllayer/xrwebgllayer) constructor's `layerInit` parameter, requests that the new WebGL rendering layer support anti-aliasing. If this property is missing or is `false`, anti-aliasing is not desired.

There is no way to request a specific anti-aliasing format or level; this decision is left up to the [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent).

Syntax
------

    let layerInit = {
      antialias: boolValue
    };
    let glLayer = new XRWebGLLayer(xrSession, gl, layerInit);

    let glLayer = new XRWebGLLayer(xrSession, gl, { antialias: boolValue });

### Value

A Boolean value which can be set to `true` to request anti-aliasing support in the new WebGL rendering layer. If `false`, anti-aliasing is not desired.

Usage notes
-----------

The state of anti-aliasing for the context after being created can be read from the [`XRWebGLLayer`](../xrwebgllayer) property [`antialias`](../xrwebgllayer/antialias).

Example
-------

In this example, before creating a new [`XRWebGLLayer`](../xrwebgllayer) to use for rendering, the value of a user preference from a configuration interface is obtained using a function called `getPreferenceValue()` to determine whether the user has enabled or disabled anti-aliasing support; this is passed into the constructor.

    let options = {
      antialias: getPreferenceValue("antialiasing")
    };

    let glLayer = new XRWebGLLayer(xrSession, gl, options);
    if (glLayer) {
      xrSession.updateRenderState({ baseLayer: glLayer });
    }

Offering the user features such as the ability to enable or disable things like anti-aliasing can provide them with optiions to try when your app isn't performing as well as they'd like. Disabling anti-aliasing may improve performance to some extent.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webxr/#dom-xrwebgllayerinit-antialias">WebXR Device API<br />
<span class="small">The definition of 'XRWebGLLayerInit.antialias' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`antialias`

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

See also
--------

-   [WebXR Device API](../webxr_device_api)
-   [Getting started with WebGL](../webgl_api/tutorial/getting_started_with_webgl)
-   [`XRWebGLLayer.antialias`](../xrwebgllayer/antialias)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XRWebGLLayerInit/antialias" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XRWebGLLayerInit/antialias</a>
