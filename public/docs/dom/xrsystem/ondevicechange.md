XRSystem: ondevicechange
========================

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `ondevicechange` property of the [`XRSystem`](../xrsystem) interface is passed a `devicechange` event whenever availability of an immersive device changes. The event that is fired is a "simple event" that implements the [`Event`](../event) interface.

Syntax
------

    navigator.xr.ondevicechange = function(event) { ... };

### Value

[`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined)

Example
-------

    navigator.xr.ondevicechange = function(ev) {
      console.log("The availability of immersive XR devices has changed.")
    };

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webxr/#dom-xrsystem-ondevicechange">WebXR Device API<br />
<span class="small">The definition of 'ondevicechange ' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`ondevicechange`

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

-   [`Event`](../event)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XRSystem/ondevicechange" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XRSystem/ondevicechange</a>
