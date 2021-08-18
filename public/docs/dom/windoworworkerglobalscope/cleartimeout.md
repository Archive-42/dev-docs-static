WindowOrWorkerGlobalScope.clearTimeout()
========================================

The `clearTimeout()` method of the [`WindowOrWorkerGlobalScope`](../windoworworkerglobalscope) mixin cancels a timeout previously established by calling [`setTimeout()`](settimeout).

Syntax
------

    scope.clearTimeout(timeoutID)

### Parameters

`timeoutID`  
The identifier of the timeout you want to cancel. This ID was returned by the corresponding call to `setTimeout()`.

It's worth noting that the pool of IDs used by [`setTimeout()`](settimeout) and [`setInterval()`](setinterval) are shared, which means you can technically use `clearTimeout()` and [`clearInterval()`](clearinterval) interchangeably. However, for clarity, you should avoid doing so.

Example
-------

Run the script below in the context of a web page and click on the page once. You'll see a message popping up in a second. If you click the page multiple times in one second, the alert only appears once.

    var alarm = {
      remind: function(aMessage) {
        alert(aMessage);
        this.timeoutID = undefined;
      },

      setup: function() {
        if (typeof this.timeoutID === 'number') {
          this.cancel();
        }

        this.timeoutID = window.setTimeout(function(msg) {
          this.remind(msg);
        }.bind(this), 1000, 'Wake up!');
      },

      cancel: function() {
        window.clearTimeout(this.timeoutID);
      }
    };
    window.onclick = function() { alarm.setup(); };

Notes
-----

Passing an invalid ID to `clearTimeout()` silently does nothing; no exception is thrown.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/webappapis.html#dom-cleartimeout">HTML Living Standard<br />
<span class="small">The definition of 'WindowOrWorkerGlobalScope.clearTimeout()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Method moved to the <code>WindowOrWorkerGlobalScope</code> mixin in the latest spec.</td></tr><tr class="even"><td><a href="https://html.spec.whatwg.org/multipage/webappapis.html#dom-cleartimeout">HTML Living Standard<br />
<span class="small">The definition of 'clearTimeout()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`clearTimeout`

45

12

1

4

From Internet Explorer 4 through 8, `clearTimeout` is an Object rather than a Function. This behavior was fixed in Internet Explorer 9.

4

4

45

45

4

10.1

1

5.0

See also
--------

-   [`WindowOrWorkerGlobalScope.setTimeout()`](settimeout)
-   [`WindowOrWorkerGlobalScope.setInterval()`](setinterval)
-   [`WindowOrWorkerGlobalScope.clearInterval()`](clearinterval)
-   [`Window.requestAnimationFrame()`](../window/requestanimationframe)
-   [*Daemons* management](https://developer.mozilla.org/en-US/docs/JavaScript/Timers/Daemons)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/clearTimeout" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/clearTimeout</a>
