XRInputSourcesChangeEventInit.added
===================================

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The [`XRInputSourcesChangeEventInit`](../xrinputsourceschangeeventinit) property [`added`](added) specifies a list of input sources, each identified using an [`XRInputSource`](../xrinputsource) object, which the represented [`inputsourceschange`](../xrsession/inputsourceschange_event) event is to indicate are newly available for use.

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

An [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) of zero or more [`XRInputSource`](../xrinputsource) objects, each representing one input device added to the XR system.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webxr/#dom-xrinputsourceschangeeventinit-added">WebXR Device API<br />
<span class="small">The definition of 'XRInputSourcesChangeEventInit.added' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

Browser compatibility
---------------------

No compatibility data found for `api.XRInputSourcesChangeEventInit.added`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XRInputSourcesChangeEventInit/added" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XRInputSourcesChangeEventInit/added</a>
