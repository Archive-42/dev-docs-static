XRSystem: devicechange event
============================

A `devicechange` event is fired on an [`XRSystem`](../xrsystem) object whenever the whenever the availability of immersive XR devices has changed; for example, a VR headset or AR goggles have been connected or disconnected. It's a generic [`Event`](../event) with no added properties.

**Note:** Not to be confused with the [`MediaDevices`](../mediadevices) [`devicechange`](../mediadevices/devicechange_event) event.

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../event"><code>Event</code></a></td></tr><tr class="even"><td>Event handler</td><td><a href="ondevicechange"><code>XRSystem.ondevicechange</code></a></td></tr></tbody></table>

Usage notes
-----------

`devicechange` events are not delivered if the document which owns the **[`XRSystem`](../xrsystem)** object has been granted permission to do so through the `xr-spatial-tracking` feature policy.

You can use this event to, for example, monitor for the availability of a WebXR-compatible device so that you can enable a UI element which the user can use to activate immersive mode. This is shown in the [example](#example) below.

Example
-------

The example shown here handles the `devicechange` event by toggling the availability of the "Enter XR" button based on whether or not any immersive devices are currently available.

    if (navigator.xr) {
      navigator.xr.addEventListener("devicechange", event => {
        navigator.xr.isSessionSupported("immersive-vr")
        .then(immersiveOK) => {
          if (immersiveOK) {
            enableXRButton.disabled = false;
          } else {
            enableXRButton.disabled = true;
          }
        });
      });
    }

When `devicechange` is received, the handler set up in this code calls the `XR` method [`isSessionSupported()`](issessionsupported) to find out if there's a device available that can handle immersive VR presentations. If there is, the button to enter XR mode is enabled; otherwise it's disabled.

You can also use the [`ondevicechange`](ondevicechange) event handler property to set a single handler for `devicechange` events:

    if (navigator.xr) {
      navigator.xr.ondevicechange = event => {
        /* ... etc ... */
      };
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webxr/#eventdef-xrsystem-devicechange">WebXR Device API<br />
<span class="small">The definition of 'devicechange event' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`devicechange_event`

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

-   [`XRSystem.ondevicechange`](ondevicechange)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XRSystem/devicechange_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XRSystem/devicechange_event</a>
