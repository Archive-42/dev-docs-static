WindowOrWorkerGlobalScope.origin
================================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `origin` read-only property of the [`WindowOrWorkerGlobalScope`](../windoworworkerglobalscope) interface returns the origin of the global scope, serialized as a string.

Syntax
------

    var myOrigin = self.origin; // or just origin

### Value

A [`USVString`](../usvstring).

Examples
--------

Executed from inside a worker script, the following snippet will log the worker's global scope's origin to the console each time it receives a message

    onmessage = function() {
      console.log(self.origin);
    };

If the origin is not a scheme/host/port tuple (say you are trying to run it locally, i.e. via `file://` URL), `origin` will return the string `"null"`.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/webappapis.html#dom-origin">HTML Living Standard<br />
<span class="small">The definition of 'WindowOrWorkerGlobalScope.origin' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`origin`

59

≤79

54

No

No

11

59

59

54

No

11

7.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/origin" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/origin</a>
