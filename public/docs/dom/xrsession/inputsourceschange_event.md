XRSession: inputsourceschange event
===================================

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `inputsourceschange` event is sent to an [`XRSession`](../xrsession) when the set of available WebXR input devices changes. The received event, of type [`XRInputSourcesChangeEvent`](../xrinputsourceschangeevent), contains a list of any newly [`added`](../xrinputsourceschangeevent/added) and/or [`removed`](../xrinputsourceschangeevent/removed) input devices.

<table><tbody><tr class="odd"><td>Bubbles</td><td>Yes</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../xrinputsourceschangeevent"><code>XRInputSourcesChangeEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td><a href="oninputsourceschange"><code>oninputsourceschange</code></a></td></tr></tbody></table>

The event object contains lists of the newly-added and/or removed input devices in its [`added`](../xrinputsourceschangeevent/added) and [`removed`](../xrinputsourceschangeevent/removed) properties.

Examples
--------

The following example shows how to set up an event handler which uses `inputsourceschange` events to detect newly-available pointing devices and to load their models in preparation to display them in the next animation frame.

    xrSession.addEventListener("inputsourceschange", onInputSourcesChange);

    function onInputSourcesChange(event) {
      for (let input of event.added) {
        if (input.targetRayMode == "tracked-pointer") {
          loadControllerMesh(input);
        }
      }
    }

You can also add a handler for `inputsourceschange` events by setting the [`oninputsourceschange`](oninputsourceschange) event handler:

    xrSession.oninputsourceschange = onInputSourcesChange;

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webxr/#eventdef-xrsession-inputsourceschange">WebXR Device API<br />
<span class="small">The definition of 'inputsourceschange event' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`inputsourceschange_event`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XRSession/inputsourceschange_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XRSession/inputsourceschange_event</a>
