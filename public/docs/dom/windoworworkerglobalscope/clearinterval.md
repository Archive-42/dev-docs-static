WindowOrWorkerGlobalScope.clearInterval()
=========================================

The `clearInterval()` method of the [`WindowOrWorkerGlobalScope`](../windoworworkerglobalscope) mixin cancels a timed, repeating action which was previously established by a call to [`setInterval()`](setinterval).

Syntax
------

    scope.clearInterval(intervalID)

### Parameters

`intervalID`  
The identifier of the repeated action you want to cancel. This ID was returned by the corresponding call to `setInterval()`.

It's worth noting that the pool of IDs used by [`setInterval()`](setinterval) and [`setTimeout()`](settimeout) are shared, which means you can technically use `clearInterval()` and [`clearTimeout()`](cleartimeout) interchangeably. However, for clarity, you should avoid doing so.

### Return value

[`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined)

Example
-------

See the [`setInterval()` examples](setinterval#examples).

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/webappapis.html#dom-clearinterval">HTML Living Standard<br />
<span class="small">The definition of 'WindowOrWorkerGlobalScope.clearInterval()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Method moved to the <code>WindowOrWorkerGlobalScope</code> mixin in the latest spec.</td></tr><tr class="even"><td><a href="https://html.spec.whatwg.org/multipage/webappapis.html#dom-clearinterval">HTML Living Standard<br />
<span class="small">The definition of 'clearInterval()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`clearInterval`

4

12

1

4

From Internet Explorer 4 through 8, `clearInterval` is an Object rather than a Function. This behavior was fixed in Internet Explorer 9.

4

4

1

18

4

10.1

1

1.0

See also
--------

-   [JavaScript timers](https://developer.mozilla.org/en-US/docs/JavaScript/Timers)
-   [`WindowOrWorkerGlobalScope.setTimeout`](settimeout)
-   [`WindowOrWorkerGlobalScope.setInterval`](setinterval)
-   [`WindowOrWorkerGlobalScope.clearTimeout`](cleartimeout)
-   [`Window.requestAnimationFrame`](../window/requestanimationframe)
-   [*Daemons* management](https://developer.mozilla.org/en-US/docs/JavaScript/Timers/Daemons)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/clearInterval" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/clearInterval</a>
