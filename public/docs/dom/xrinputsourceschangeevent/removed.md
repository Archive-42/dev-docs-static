XRInputSourcesChangeEvent.removed
=================================

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The read-only [`XRInputSourcesChangeEvent`](../xrinputsourceschangeevent) property [`removed`](removed) is an array of zero or more [`XRInputSource`](../xrinputsource) objects representing the input sources which have been removed from the [`XRSession`](../xrsession).

Syntax
------

    removedInputs = xrInputSourcesChangeEvent.removed;

### Value

An [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) of zero or more [`XRInputSource`](../xrinputsource) objects, each representing one input device removed from the XR system.

Examples
--------

The example below creates a handler for the [`inputsourceschange`](../xrsession/inputsourceschange_event) event that processes the lists of added and removed from the WebXR system. It looks for new and removed devices whose [`targetRayMode`](../xrinputsource/targetraymode) is `tracked-pointer`.

    xrSession.oninputsourcescchange = event => {
      for (let input of event.added) {
        if (input.targetRayMode == "tracked-pointer") {
          addedPointerDevice(input);
        }
      }
      for (let input of event.removed) {
        if (input.targetRayMode == "tracked-pointer") {
          removedPointerDevice(input);
        }
      }
    };

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webxr/#dom-xrinputsourceschangeevent-removed">WebXR Device API<br />
<span class="small">The definition of 'XRInputSourcesChangeEvent.removed' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`removed`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XRInputSourcesChangeEvent/removed" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XRInputSourcesChangeEvent/removed</a>
