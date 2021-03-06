XRInputSourceEventInit.inputSource
==================================

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The [`XRInputSourceEventInit`](../xrinputsourceeventinit) dictionary's `inputSource` property is used when calling the [`XRInputSourceEvent()`](../xrinputsourceevent/xrinputsourceevent) constructor to specify the [`XRInputSource`](../xrinputsource) from which the newly-created event is being sent.

Of course, as a general rule, you won't need to create `XRInputSourceEventInit` objects yourself. These events are generated by and sent to you by the WebXR infrastructure.

Syntax
------

    let xrInputSourceEventInit.inputSource = xrInputSource;

    let xrInputSourceEventInit = { inputSource: xrInputSource };

    let xrInputSourceEvent = new XRInputSourceEvent(type, { inputSource: xrInputSource });

### Value

An [`XRInputSource`](../xrinputsource) object indicating the source of the newly-created [`XRInputSourceEvent`](../xrinputsourceevent) to be created. The new object's [`inputSource`](../xrinputsourceevent/inputsource) will be set to this value.

Examples
--------

This example creates a new [`select`](../xrsession/select_event) event and sends it to the [`XRSession`](../xrsession).

    let event = new XRInputSourceEvent("select", {
      frame: eventFrame,
      inputSource: source
    };
    if (event) {
      xrSession.dispatchEvent(event);
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webxr/#dom-xrinputsourceeventinit-inputsource">WebXR Device API<br />
<span class="small">The definition of 'XRInputSourceEventInit.inputSource' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

Browser compatibility
---------------------

No compatibility data found for `api.XRInputSourceEventInit.inputSource`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XRInputSourceEventInit/inputSource" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XRInputSourceEventInit/inputSource</a>
