window.cancelIdleCallback()
===========================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

Summary
-------

The `window.cancelIdleCallback()` method cancels a callback previously scheduled with [`window.requestIdleCallback()`](requestidlecallback).

Syntax
------

    window.cancelIdleCallback(handle);

### Parameters

`handle`  
The ID value returned by [`window.requestIdleCallback()`](requestidlecallback) when the callback was established.

### Return value

`undefined`.

Example
-------

See our [complete example](../background_tasks_api#example) in the article [Cooperative Scheduling of Background Tasks API](../background_tasks_api).

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/requestidlecallback/">Cooperative Scheduling of Background Tasks</a></td><td><span class="spec-pr">Proposed Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`cancelIdleCallback`

47

79

55

No

Yes

No

47

47

55

Yes

No

5.0

See also
--------

-   [A polyfill](https://github.com/behnammodi/polyfill/blob/master/window.polyfill.js)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Window/cancelIdleCallback" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Window/cancelIdleCallback</a>
