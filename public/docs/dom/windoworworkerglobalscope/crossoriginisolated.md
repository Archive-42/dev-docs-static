WindowOrWorkerGlobalScope.crossOriginIsolated
=============================================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `crossOriginIsolated` read-only property of the [`WindowOrWorkerGlobalScope`](../windoworworkerglobalscope) interface returns a boolean value that indicates whether a [`SharedArrayBuffer`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/SharedArrayBuffer) can be sent via a [`Window.postMessage()`](../window/postmessage) call.

This value is dependant on any [`Cross-Origin-Opener-Policy`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Cross-Origin-Opener-Policy) and [`Cross-Origin-Embedder-Policy`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Cross-Origin-Embedder-Policy) headers present in the response.

Syntax
------

    var myCrossOriginIsolated = self.crossOriginIsolated; // or just crossOriginIsolated

### Value

A boolean value

Examples
--------

    if(crossOriginIsolated) {
      // Post SharedArrayBuffer
    } else {
      // Do something else
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-crossoriginisolated">HTML Living Standard<br />
<span class="small">The definition of '<code>crossOriginIsolated</code>' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`crossOriginIsolated`

87

87

72

No

73

No

No

87

No

No

No

14.0

See also
--------

-   [Service Workers](../service_worker_api)
-   [Web Workers](../web_workers_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/crossOriginIsolated" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/crossOriginIsolated</a>
