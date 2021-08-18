XRSessionEventInit.session
==========================

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The [`XRSessionEventInit`](../xrsessioneventinit) dictionary's `session` property specifies the [`XRSession`](../xrsession) for which the event describes a state change.

Syntax
------

    let sessionEventInit = {
      session: xrSession
    };
    mySessionEvent = new XRSessionEvent(type, sessionEventInit);

    mySessionEvent = new XRSessionEvent(type,
                     { session: XRSession });

### Value

An [`XRSession`](../xrsession) object indicating which WebXR session the event is referring to.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webxr/#dom-xrsessioneventinit-session">WebXR Device API<br />
<span class="small">The definition of 'XRSessionEventInit.session' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

Browser compatibility
---------------------

No compatibility data found for `api.XRSessionEventInit.session`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XRSessionEventInit/session" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XRSessionEventInit/session</a>
