XRInputSourceEventInit
======================

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `XRInputSourceEventInit` dictionary is used when calling the [`XRInputSourceEvent()`](xrinputsourceevent/xrinputsourceevent) constructor to provide configuration options for the newly-created [`XRInputSourceEvent`](xrinputsourceevent) object to take on.

Properties
----------

The `XRInputSourceEventInit` dictionary inherits properties from the <span class="page-not-created">`EventInit`</span> dictionary. It also offers the following:

[`frame`](xrinputsourceeventinit/frame)  
An [`XRFrame`](xrframe) object representing the event frame during which the event took place. This event is *not* associated with the animation process, and has no viewer information contained within it.

[`inputSource`](xrinputsourceeventinit/inputsource)  
An [`XRInputSource`](xrinputsource) object representing the input device from which the event is being sent.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webxr/#dictdef-xrinputsourceeventinit">WebXR Device API<br />
<span class="small">The definition of 'XRInputSourceEventInit' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

Browser compatibility
---------------------

No compatibility data found for `api.XRInputSourceEventInit`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XRInputSourceEventInit" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XRInputSourceEventInit</a>
