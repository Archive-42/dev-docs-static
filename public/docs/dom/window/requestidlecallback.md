window.requestIdleCallback()
============================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `window.requestIdleCallback()` method queues a function to be called during a browser's idle periods. This enables developers to perform background and low priority work on the main event loop, without impacting latency-critical events such as animation and input response. Functions are generally called in first-in-first-out order; however, callbacks which have a `timeout` specified may be called out-of-order if necessary in order to run them before the timeout elapses.

You can call `requestIdleCallback()` within an idle callback function to schedule another callback to take place no sooner than the next pass through the event loop.

A `timeout` option is strongly recommended for required work, as otherwise it's possible multiple seconds will elapse before the callback is fired.

Syntax
------

    var handle = window.requestIdleCallback(callback[, options])

### Return value

An ID which can be used to cancel the callback by passing it into the [`window.cancelIdleCallback()`](cancelidlecallback) method.

### Parameters

`callback`  
A reference to a function that should be called in the near future, when the event loop is idle. The callback function is passed an [`IdleDeadline`](../idledeadline) object describing the amount of time available and whether or not the callback has been run because the timeout period expired.

 `options` <span class="badge inline optional">Optional</span>   
Contains optional configuration parameters. Currently only one property is defined:

-   `timeout`: If `timeout` is specified and has a positive value, and the callback has not already been called by the time *timeout* milliseconds have passed, a task to execute the callback is queued in the event loop, even if doing so risks causing a negative performance impact.

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

`requestIdleCallback`

47

79

55

No

34

No

47

47

55

34

No

5.0

See also
--------

-   [`window.cancelIdleCallback()`](cancelidlecallback)
-   [`IdleDeadline`](../idledeadline)
-   [`window.setTimeout()`](../windoworworkerglobalscope/settimeout)
-   [`window.setInterval()`](../windoworworkerglobalscope/setinterval)
-   [`window.requestAnimationFrame`](../window/requestanimationframe)
-   [A polyfill](https://github.com/behnammodi/polyfill/blob/master/window.polyfill.js)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Window/requestIdleCallback" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Window/requestIdleCallback</a>
