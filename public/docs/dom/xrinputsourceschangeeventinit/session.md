XRInputSourcesChangeEventInit.session
=====================================

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The [`XRInputSourcesChangeEventInit`](../xrinputsourceschangeeventinit) property [`session`](session) specifies the [`XRSession`](../xrsession) to which the input source list change event applies.

Syntax
------

    let inputSourcesEventInit = {
      session: xrSession,
      added: [newDevice1, ..., newDeviceN],
      removed: [removedDevice1, ..., newDeviceN],
    };
    myInputSourcesChangeEvent = new XRInputSourcesChangeEventInit("inputsourceschange", inputSourcesEventInit);

    myInputSourcesChangeEvent = new XRInputSourcesChangeEventInit("inputsourceschange",
                                {
                                  session: xrSession,
                                  added: addedDeviceList,
                                  removed: removedDeviceList
                                });

### Value

An [`XRSession`](../xrsession) indicating the WebXR session to which the input source list change applies.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webxr/#dom-xrinputsourceschangeeventinit-session">WebXR Device API<br />
<span class="small">The definition of 'XRInputSourcesChangeEventInit.session' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

Browser compatibility
---------------------

No compatibility data found for `api.XRInputSourcesChangeEventInit.session`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XRInputSourcesChangeEventInit/session" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XRInputSourcesChangeEventInit/session</a>
