XRInputSourceEvent.inputSource
==============================

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The [`XRInputSourceEvent`](../xrinputsourceevent) interface's read-only `inputSource` property specifies the [`XRInputSource`](../xrinputsource) which generated the input event. This information lets you handle the event appropriately given the particulars of the user input device being manipulated.

Syntax
------

    let inputSource = xrInputSourceEvent.inputSource;

### Value

An [`XRInputSource`](../xrinputsource) object identifying the source of the user input event. This event indicates an action the user has taken using a WebXR input controller, such as a hand controller, motion sensing device, or other input apparatus.

Example
-------

The snippet below shows a handler for the [`select`](../xrsession/select_event) event which looks specifically for events which happen on `gaze` input devices. The device type is identified by looking at the [`XRInputSource`](../xrinputsource) in `inputSource` and its [`targetRayMode`](../xrinputsource/targetraymode) property.

    xrSession.onselect = event => {
      let source = event.inputSource;

      if (source.targetRayMode == "gaze") {
        /* handle selection using a gaze input */
      }
    };

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webxr/#dom-xrinputsourceevent-inputsource">WebXR Device API<br />
<span class="small">The definition of 'XRInputSourceEvent.inputSource' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`inputSource`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XRInputSourceEvent/inputSource" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XRInputSourceEvent/inputSource</a>
