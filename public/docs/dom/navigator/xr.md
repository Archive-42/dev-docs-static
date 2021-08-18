Navigator.xr
============

The read-only `xr` property provided by the [`Navigator`](../navigator) or [`WorkerNavigator`](../workernavigator) interface returns an [`XRSystem`](../xrsystem) object which can be used to access the [WebXR Device API](../webxr_device_api).

Syntax
------

    const xr = navigator.xr

### Value

The [`XRSystem`](../xrsystem) object used to interface with the [WebXR Device API](../webxr_device_api) in the current context. This can be used to present augmented and/or virtual reality imagery to the user.

Usage notes
-----------

Each [`Window`](../window) has its own instance of [`Navigator`](../navigator), which can be accessed as [`window.navigator`](../window/navigator) or as [`navigator`](../window/navigator). At the same time, a new [`XRSystem`](../xrsystem) instance is also created and attached to the `navigator` instance as [`navigator.xr`](xr). If the `xr` property exists, you can use it to access the [WebXR Device API](../webxr_device_api).

To determine if WebXR is available, you can do something like this:

    if ("xr" in window.navigator) {
      /* WebXR can be used! */
    } else {
      /* WebXR isn't available */
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webxr/#navigator-xr-attribute">WebXR Device API<br />
<span class="small">The definition of 'Navigator.xr' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`xr`

79

79

No

No

No

No

No

79

No

No

No

11.2

See also
--------

-   [WebGL API](../webgl_api): 2D and 3D accelerated graphics for the web
-   [Canvas API](../canvas_api): Easy 2D graphics API

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Navigator/xr" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Navigator/xr</a>
