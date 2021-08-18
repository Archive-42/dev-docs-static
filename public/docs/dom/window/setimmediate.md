Window.setImmediate()
=====================

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

This method is used to break up long running operations and run a callback function immediately after the browser has completed other operations such as events and display updates.

This method is not expected to become standard, and is only implemented by recent builds of Internet Explorer and Node.js 0.10+. It meets resistance both from [Gecko](https://bugzilla.mozilla.org/show_bug.cgi?id=686201) (Firefox) and [Webkit](https://code.google.com/p/chromium/issues/detail?id=146172) (Google/Apple).

Syntax
------

    var immediateID = setImmediate(func, [param1, param2, ...]);
    var immediateID = setImmediate(func);

-   where `immediateID` is the ID of the immediate which can be used later with [`window.clearImmediate`](clearimmediate).
-   `func` is the function you wish to call.

All parameters will be passed directly to your function.

Notes
-----

The [`clearImmediate`](clearimmediate) method can be used to clear the immediate actions, just like [`clearTimeout`](../windoworworkerglobalscope/cleartimeout) for [`setTimeout`](../windoworworkerglobalscope/settimeout).

This method can be used instead of the `setTimeout(fn, 0)` method to execute [heavy operations](https://www.nczonline.net/blog/2009/08/11/timed-array-processing-in-javascript/).

The feature can be emulated in a few different ways:

-   <span style="line-height: 22px;">[`postMessage`](postmessage) </span>can be used to trigger an immediate but yielding callback. Do note that Internet Explorer 8 includes a synchronous version of `postMessage`, which means it cannot be used as a fallback.
-   [`MessageChannel`](../messagechannel) can be used reliably inside of Web Workers whereas the semantics of postMessage mean it cannot be used there.
-   `setTimeout(fn, 0)` *can* potentially be used, however as it is clamped to 4ms for timers nested more than 5 levels deep [per the HTML spec](https://html.spec.whatwg.org/multipage/webappapis.html#timers), it does not make for a suitable polyfill for the natural immediacy of `setImmediate`.

All of these techniques are incorporated into a [robust setImmediate polyfill](https://github.com/NobleJS/setImmediate).

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/setImmediate/#si-setImmediate">Efficient Script Yielding<br />
<span class="small">The definition of '<code>setImmediate</code>' in that specification.</span></a></td><td><span class="spec-ED">Editor's Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`setImmediate`

No

12-79

No

10

No

No

No

No

No

No

No

No

See also
--------

-   [`Window.clearImmediate()`](clearimmediate)
-   [Microsoft `setImmediate` API Demo](http://ie.microsoft.com/testdrive/Performance/setImmediateSorting/Default.html)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Window/setImmediate" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Window/setImmediate</a>
