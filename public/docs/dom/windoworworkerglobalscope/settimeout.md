WindowOrWorkerGlobalScope.setTimeout()
======================================

The `setTimeout()` method of the [`WindowOrWorkerGlobalScope`](../windoworworkerglobalscope) [mixin](https://developer.mozilla.org/en-US/docs/Glossary/Mixin) (and successor to `Window.setTimeout()`) sets a timer which executes a function or specified piece of code once the timer expires.

Syntax
------

    var timeoutID = scope.setTimeout(function[, delay, arg1, arg2, ...]);
    var timeoutID = scope.setTimeout(function[, delay]);
    var timeoutID = scope.setTimeout(code[, delay]);

### Parameters

`function`  
A [`function`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function) to be executed after the timer expires.

`code`  
An alternative syntax that allows you to include a string instead of a function, which is compiled and executed when the timer expires. This syntax is **not recommended** for the same reasons that make using [`eval()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/eval) a security risk.

 `delay` <span class="badge inline optional">Optional</span>   
The time, in milliseconds (thousandths of a second), the timer should wait before the specified function or code is executed. If this parameter is omitted, a value of 0 is used, meaning execute "immediately", or more accurately, the next event cycle. Note that in either case, the actual delay may be longer than intended; see [Reasons for delays longer than specified](#reasons_for_delays_longer_than_specified) below.

 `arg1, ..., argN` <span class="badge inline optional">Optional</span>   
Additional arguments which are passed through to the function specified by `function`.

**Note**: Passing additional parameters to the function in the first syntax does not work in Internet Explorer 9 and below. If you want to enable this functionality on that browser, you must use a polyfill (see the [Polyfill](#polyfill) section).

### Return value

The returned `timeoutID` is a positive integer value which identifies the timer created by the call to `setTimeout()`; this value can be passed to [`clearTimeout()`](cleartimeout) to cancel the timeout.

It may be helpful to be aware that `setTimeout()` and [`setInterval()`](setinterval) share the same pool of IDs, and that `clearTimeout()` and [`clearInterval()`](clearinterval) can technically be used interchangeably. For clarity, however, you should try to always match them to avoid confusion when maintaining your code.

It is guaranteed that a timeout ID will never be reused by a subsequent call to `setTimeout()` or `setInterval()` on the same object (a window or a worker). However, different objects use separate pools of IDs.

Examples
--------

1: setTimeout() / clearTimeout()
--------------------------------

The following example sets up two simple buttons in a web page and hooks them to the `setTimeout()` and `clearTimeout()` routines. Pressing the first button will set a timeout which calls an alert dialog after two seconds and stores the timeout id for use by `clearTimeout()`. You may optionally cancel this timeout by pressing on the second button.

### HTML

    <p>Live Example</p>
    <button onclick="delayedAlert();">Show an alert box after two seconds</button>
    <p></p>
    <button onclick="clearAlert();">Cancel alert before it happens</button>

### JavaScript

    var timeoutID;

    function delayedAlert() {
      timeoutID = window.setTimeout(window.alert, 2*1000, 'That was really slow!');
    }

    function clearAlert() {
      window.clearTimeout(timeoutID);
    }

### Result

See also [`clearTimeout()` example](cleartimeout#example).

2: Timeouts throttled
---------------------

This example defines functions which demonstrate this throttling effect:

-   *`interval()`*, called after `setInterval()` interval expiration.
-   *`timeout()`* called after `setTimeout()` timer expiration.
-   *`run()`*, called at program start.
-   *`logline()`*, called at interval and timer expiration, displays the last and current intervals along with an indicator when throttling occurs.

The durations defined for `interval()` and `timeout()` cause both timers to immediately expire which triggers their completion functions. The browser applies call throttling when it senses that it's calling these completion functions in rapid succession.

### HTML

    <p>Live Example</p>
    <button onclick="run();">Run</button>
    <div id="log"></div>

### JavaScript

    var to_timer = 0; // duration is zero milliseconds
    var interval_timer = 0; // expires immediately
    var cleanup_timer = 0; // fires at end of run
    var last = 0; // last millisecond recorded
    var duration = 15; // run duration in milliseconds
    var lineno = 0; // current output line number

    function interval() {
      var d = new Date();
      logline(d.getMilliseconds());
    }

    function timeout() {
      var d = new Date();
      logline(d.getMilliseconds());
      interval();
      to_timer = setTimeout(timeout, 0);
    }

    function run() {
      interval_timer = setInterval(interval, 0);
      to_timer = setTimeout(timeout, 0);
      cleanup_timer = setInterval(cleanup, duration);
      last = 0;
      lineno = 0;
      document.getElementById("log").innerHTML = "";
      document.getElementById("log").innerHTML = "line last current";
     }

    function logline(msec) { // msec can't wrap: run duration > 1 second
      var c = "";
      if ((last != 0) && (last > msec - 1 /* variation */)) { c = "Throttled"; }
      document.getElementById("log").innerHTML +=  "<pre>" + pad(lineno++, 2) + "  " + pad(last, 3) + "  " + msec + " " + c;
      last = msec;
    }

### Result

Polyfill
--------

If you need to pass one or more arguments to your callback function, but need it to work in browsers which don't support sending additional arguments using either `setTimeout()` or `setInterval()` (e.g., Internet Explorer 9 and below), you can include this polyfill to enable the HTML5 standard arguments-passing functionality. Just add this code to the top of your script:

    /*\
    |*|
    |*|  Polyfill which enables the passage of arbitrary arguments to the
    |*|  callback functions of JavaScript timers (HTML5 standard syntax).
    |*|
    |*|  https://developer.mozilla.org/en-US/docs/DOM/window.setInterval
    |*|
    |*|  Syntax:
    |*|  var timeoutID = window.setTimeout(func, delay[, arg1, arg2, ...]);
    |*|  var timeoutID = window.setTimeout(code, delay);
    |*|  var intervalID = window.setInterval(func, delay[, arg1, arg2, ...]);
    |*|  var intervalID = window.setInterval(code, delay);
    |*|
    \*/

    (function() {
      setTimeout(function(arg1) {
        if (arg1 === 'test') {
          // feature test is passed, no need for polyfill
          return;
        }
        var __nativeST__ = window.setTimeout;
        window.setTimeout = function(vCallback, nDelay /*, argumentToPass1, argumentToPass2, etc. */ ) {
          var aArgs = Array.prototype.slice.call(arguments, 2);
          return __nativeST__(vCallback instanceof Function ? function() {
            vCallback.apply(null, aArgs);
          } : vCallback, nDelay);
        };
      }, 0, 'test');

      var interval = setInterval(function(arg1) {
        clearInterval(interval);
        if (arg1 === 'test') {
          // feature test is passed, no need for polyfill
          return;
        }
        var __nativeSI__ = window.setInterval;
        window.setInterval = function(vCallback, nDelay /*, argumentToPass1, argumentToPass2, etc. */ ) {
          var aArgs = Array.prototype.slice.call(arguments, 2);
          return __nativeSI__(vCallback instanceof Function ? function() {
            vCallback.apply(null, aArgs);
          } : vCallback, nDelay);
        };
      }, 0, 'test');
    }())

### IE-only fix

If you want a completely unobtrusive fix for every other mobile or desktop browser, including IE 9 and below, you can either use JavaScript conditional comments:

    /*@cc_on
      // conditional IE < 9 only fix
      @if (@_jscript_version <= 9)
      (function(f){
         window.setTimeout = f(window.setTimeout);
         window.setInterval = f(window.setInterval);
      })(function(f){return function(c,t){var a=[].slice.call(arguments,2);return f(function(){c instanceof Function?c.apply(this,a):eval(c)},t)}});
      @end
    @*/

... or go for a very clean approach based on the IE HTML conditional feature:

    <!--[if lte IE 9]><script>
    (function(f){
    window.setTimeout=f(window.setTimeout);
    window.setInterval=f(window.setInterval);
    })(function(f){return function(c,t){
    var a=[].slice.call(arguments,2);return f(function(){c instanceof Function?c.apply(this,a):eval(c)},t)}
    });
    </script><![endif]-->

### Workarounds

Another possibility is to use an anonymous function to call your callback, but this solution is a bit more expensive. Example:

    var intervalID = setTimeout(function() { myFunc('one', 'two', 'three'); }, 1000);

The above example can also be written with the help of an [arrow function](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions):

    var intervalID = setTimeout(() => { myFunc('one', 'two', 'three'); }, 1000);

Yet another possibility is to use [function's `bind`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function/bind). Example:

    setTimeout(function(arg1){}.bind(undefined, 10), 1000);

The "this" problem
------------------

When you pass a method to `setTimeout()` (or any other function, for that matter), it will be invoked with a `this` value that may differ from your expectation. This issue is explained in detail in the [JavaScript reference](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/this#as_an_object_method).

### Explanation

Code executed by `setTimeout()` is called from an execution context separate from the function from which `setTimeout` was called. The usual rules for setting the `this` keyword for the called function apply, and if you have not set `this` in the call or with `bind`, it will default to the `window` (or `global`) object. It will not be the same as the `this` value for the function that called `setTimeout`.

See the following example:

    myArray = ['zero', 'one', 'two'];
    myArray.myMethod = function (sProperty) {
      alert(arguments.length > 0 ? this[sProperty] : this);
    };

    myArray.myMethod(); // prints "zero,one,two"
    myArray.myMethod(1); // prints "one"

The above works because when `myMethod` is called, its `this` is set to `myArray` by the call, so within the function, `this[sProperty]` is equivalent to `myArray[sProperty]`. However, in the following:

    setTimeout(myArray.myMethod, 1.0*1000); // prints "[object Window]" after 1 second
    setTimeout(myArray.myMethod, 1.5*1000, '1'); // prints "undefined" after 1.5 seconds

The `myArray.myMethod` function is passed to `setTimeout`, then when it's called, its `this` is not set so it defaults to the `window` object. There's also no option to pass a `thisArg` to setTimeout as there is in Array methods like forEach, reduce, etc. and as shown below, using `call` to set `this` doesn't work either.

    setTimeout.call(myArray, myArray.myMethod, 2.0*1000); // error: "NS_ERROR_XPC_BAD_OP_ON_WN_PROTO: Illegal operation on WrappedNative prototype object"
    setTimeout.call(myArray, myArray.myMethod, 2.5*1000, 2); // same error

### Possible solutions

A common way to solve the problem is to use a wrapper function that sets `this` to the required value:

    setTimeout(function(){myArray.myMethod()}, 2.0*1000); // prints "zero,one,two" after 2 seconds
    setTimeout(function(){myArray.myMethod('1')}, 2.5*1000); // prints "one" after 2.5 seconds

Arrow functions are a possible alternative, too:

    setTimeout(() => {myArray.myMethod()}, 2.0*1000); // prints "zero,one,two" after 2 seconds
    setTimeout(() => {myArray.myMethod('1')}, 2.5*1000); // prints "one" after 2.5 seconds

Another possible way to solve the "`this`" problem is to replace the host `setTimeout()` and `setInterval()` global functions with ones that allow passing a `this` object and set it in the callback using [`Function.prototype.call`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function/call), e.g.:

    // Enable setting 'this' in JavaScript timers

    var __nativeST__ = window.setTimeout,
        __nativeSI__ = window.setInterval;

    window.setTimeout = function (vCallback, nDelay /*, argumentToPass1, argumentToPass2, etc. */) {
      var oThis = this,
          aArgs = Array.prototype.slice.call(arguments, 2);
      return __nativeST__(vCallback instanceof Function ? function () {
        vCallback.apply(oThis, aArgs);
      } : vCallback, nDelay);
    };

    window.setInterval = function (vCallback, nDelay /*, argumentToPass1, argumentToPass2, etc. */) {
      var oThis = this,
          aArgs = Array.prototype.slice.call(arguments, 2);
      return __nativeSI__(vCallback instanceof Function ? function () {
        vCallback.apply(oThis, aArgs);
      } : vCallback, nDelay);
    };

**Note**: These two replacements will also enable the HTML5 standard passage of arbitrary arguments to the callback functions of timers in IE. So they can be used as polyfills also. See the [Callback arguments](#callback_arguments) paragraph.

New feature test:

    myArray = ['zero', 'one', 'two'];
    myArray.myMethod = function (sProperty) {
        alert(arguments.length > 0 ? this[sProperty] : this);
    };

    setTimeout(alert, 1500, 'Hello world!'); // the standard use of setTimeout and setInterval is preserved, but...
    setTimeout.call(myArray, myArray.myMethod, 2.0*1000); // prints "zero,one,two" after 2 seconds
    setTimeout.call(myArray, myArray.myMethod, 2.5*1000, 2); // prints "two" after 2.5 seconds

**Note**: JavaScript 1.8.5 introduced the `Function.prototype.bind()` method to set the value of `this` for all calls to a given function. This can avoid having to use a wrapper function to set the value of `this` in a callback.

Example using `bind()`:

    myArray = ['zero', 'one', 'two'];
    myBoundMethod = (function (sProperty) {
        console.log(arguments.length > 0 ? this[sProperty] : this);
    }).bind(myArray);

    myBoundMethod(); // prints "zero,one,two" because 'this' is bound to myArray in the function
    myBoundMethod(1); // prints "one"
    setTimeout(myBoundMethod, 1.0*1000); // still prints "zero,one,two" after 1 second because of the binding
    setTimeout(myBoundMethod, 1.5*1000, "1"); // prints "one" after 1.5 seconds

Notes
-----

Timeouts are cancelled using [`clearTimeout()`](cleartimeout).

To call a function repeatedly (e.g., every N milliseconds), consider using [`setInterval()`](setinterval).

### Passing string literals

Passing a string instead of a function to `setTimeout()` has the same associated problems as using `eval. `

    // Recommended
    window.setTimeout(function() {
      alert('Hello World!');
    }, 500);

    // Not recommended
    window.setTimeout("alert('Hello World!');", 500);

A string passed to `setTimeout()` is evaluated in the global context, so local symbols in the context where `setTimeout()` was called will not be available when the string is evaluated as code.

### Reasons for delays longer than specified

There are a number of reasons why a timeout may take longer to fire than anticipated. This section describes the most common reasons.

#### Clamping

In modern browsers, `setTimeout()`/[`setInterval()`](setinterval) calls are throttled to a minimum of once every 4 ms when successive calls are triggered due to callback nesting (where the nesting level is at least a certain depth), or after certain number of successive intervals.

See [2 Timeouts throttled](#2_timeouts_throttled) example, above.

In Chrome and Firefox, the 5th successive callback call is clamped; Safari clamps on the 6th call; in Edge it's the 3rd one. Gecko started to clamp after 4ms `setInterval()` in [version 56](https://developer.mozilla.org/en-US/docs/Mozilla/Firefox/Releases/56). It already did this with `setTimeout()`, as described in the following notes.

[Historically](https://code.google.com/p/chromium/issues/detail?id=792#c10) some browsers implemented this throttling behavior a bit differently (e.g. Firefox) — on `setInterval()` calls made from anywhere, or when a nested `setTimeout()` is called where the nesting level is at least a certain depth.

To implement a 0 ms timeout in a modern browser, you can use [`window.postMessage()`](../window/postmessage) as [described here](https://dbaron.org/log/20100309-faster-timeouts).

The minimum delay, `DOM_MIN_TIMEOUT_VALUE`, is 4 ms (stored in a preference in Firefox: `dom.min_timeout_value`), with a `DOM_CLAMP_TIMEOUT_NESTING_LEVEL` of 5.

4 ms is [specified by the HTML5 spec](https://www.whatwg.org/specs/web-apps/current-work/multipage/timers.html#timers) and is consistent across browsers released in 2010 and onward. Prior to (Firefox 5.0 / Thunderbird 5.0 / SeaMonkey 2.2), the minimum timeout value for nested timeouts was 10 ms.

#### Timeouts in inactive tabs throttled to ≥ 1000ms

To reduce the load (and associated battery usage) from background tabs, timeouts are throttled to firing no more often than once per second (1,000 ms) in inactive tabs.

Firefox implements this behavior since version 5 (see [bug 633421](https://bugzilla.mozilla.org/show_bug.cgi?id=633421), the 1000ms constant can be tweaked through the <span class="comment-copy">`dom.min_background_timeout_value` preference).</span> Chrome implements this behavior since version 11 ([crbug.com/66078](https://crbug.com/66078)).

Firefox for Android uses a timeout value of 15 minutes for background tabs since [bug 736602](https://bugzilla.mozilla.org/show_bug.cgi?id=736602) in Firefox 14, and background tabs can also be unloaded entirely.

Firefox 50 no longer throttles background tabs if a Web Audio API [`AudioContext`](../audiocontext) is actively playing sound. Firefox 51 further amends this such that background tabs are no longer throttled if an [`AudioContext`](../audiocontext) is present in the tab at all, even if no sound is being played. These resolve a number of issues with apps which play note-based music not being able to time or synchronize the music properly when the tab is in the background.

#### Throttling of tracking timeout scripts

Since Firefox 55, tracking scripts (e.g. Google Analytics, any script URL that Firefox recognises as a tracking script through its [TP lists](https://wiki.mozilla.org/Security/Tracking_protection#Lists)) have been subject to further throttling. When running in the foreground, the throttling minimum delay is still 4ms. In background tabs, however, the throttling minimum delay is 10,000 ms, or 10 seconds, which comes into effect 30 seconds after a document has first loaded.

The prefs that control this behavior are:

-   `dom.min_tracking_timeout_value`: 4
-   `dom.min_tracking_background_timeout_value`: 10000
-   `dom.timeout.tracking_throttling_delay`: 30000

#### Late timeouts

In addition to [Clamping](#clamping), the timeout can also fire later when the page (or the OS/browser itself) is busy with other tasks. One important case to note is that the function or code snippet cannot be executed until the thread that called `setTimeout()` has terminated. For example:

    function foo() {
      console.log('foo has been called');
    }
    setTimeout(foo, 0);
    console.log('After setTimeout');

Will write to the console:

    After setTimeout
    foo has been called

This is because even though `setTimeout` was called with a delay of zero, it's placed on a queue and scheduled to run at the next opportunity; not immediately. Currently-executing code must complete before functions on the queue are executed, thus the resulting execution order may not be as expected.

#### Deferral of timeouts during pageload

Starting in Firefox 66, Firefox will defer firing setTimeout and setInterval timers while the current tab is loading. Firing is deferred until the MainThread is deemed idle (similar to [window.requestIdleCallback()](../window/requestidlecallback)), or until the load event is fired.

### WebExtension background pages and timers

In [WebExtension](https://developer.mozilla.org/en-US/docs/Mozilla/Add-ons/WebExtensions) background pages, timers don't work properly. This is because background pages don't actually stay loaded all the time: the browser can unload them if they are not being used, and restore them when they are needed. This is mostly transparent to the extension, but some things (including JS timers) won't work across an unload/restore cycle, so background pages are encouraged instead to use alarms, which will work. There's some more detail on this at [Migrate to Event Driven Background Scripts](https://developer.chrome.com/extensions/background_migration).

At the time of writing, only Chrome exhibited the above behavior — Firefox doesn't yet do the unload/restore behavior, so timers will work. But it's still a good idea to avoid timers in WebExtensions, for a couple of reasons:

1.  Compat with Chrome.
2.  Future changes in behavior that may cause problems.

### Maximum delay value

Browsers including Internet Explorer, Chrome, Safari, and Firefox store the delay as a 32-bit signed integer internally. This causes an integer overflow when using delays larger than 2,147,483,647 ms (about 24.8 days), resulting in the timeout being executed immediately.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/webappapis.html#dom-settimeout">HTML Living Standard<br />
<span class="small">The definition of 'WindowOrWorkerGlobalScope.setTimeout()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Method moved to the <code>WindowOrWorkerGlobalScope</code> mixin in the latest spec.</td></tr><tr class="even"><td><a href="https://html.spec.whatwg.org/multipage/webappapis.html#dom-settimeout">HTML Living Standard<br />
<span class="small">The definition of 'WindowTimers.setTimeout()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition (DOM Level 0)</td></tr></tbody></table>

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

`setTimeout`

30

12

1

4

4

1

4.4

30

4

10.1

1

3.0

`supports_parameters_for_callback`

Yes

12

Yes

10

Yes

?

Yes

Yes

?

?

?

Yes

`tracking_throttling`

?

?

55

?

?

?

?

?

55

?

?

?

See also
--------

-   [`WindowOrWorkerGlobalScope.clearTimeout`](cleartimeout)
-   [`WindowOrWorkerGlobalScope.setInterval`](setinterval)
-   [`window.requestAnimationFrame`](../window/requestanimationframe)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/setTimeout" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/setTimeout</a>
