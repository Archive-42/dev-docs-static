Window.requestAnimationFrame()
==============================

The `window.requestAnimationFrame()` method tells the browser that you wish to perform an animation and requests that the browser calls a specified function to update an animation before the next repaint. The method takes a callback as an argument to be invoked before the repaint.

**Note:** Your callback routine must itself call `requestAnimationFrame()` again if you want to animate another frame at the next repaint. `requestAnimationFrame()` is 1 shot.

You should call this method whenever you're ready to update your animation onscreen. This will request that your animation function be called before the browser performs the next repaint. The number of callbacks is usually 60 times per second, but will generally match the display refresh rate in most web browsers as per W3C recommendation. `requestAnimationFrame()` calls are paused in most browsers when running in background tabs or hidden [`<iframe>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe)s in order to improve performance and battery life.

The callback method is passed a single argument, a [`DOMHighResTimeStamp`](../domhighrestimestamp), which indicates the current time (based on the number of milliseconds since [time origin](../domhighrestimestamp#the_time_origin)). When multiple callbacks queued by `requestAnimationFrame()` begin to fire in a single frame, each receives the same timestamp even though time has passed during the computation of every previous callback's workload (in the code example below we only animate the frame when the timestamp changes, i.e. on the first callback). This timestamp is a decimal number, in milliseconds, but with a minimal precision of 1ms (1000 µs).

Be sure to always use the first argument (or some other method for getting the current time) to calculate how much the animation will progress in a frame, **otherwise the animation will run faster on high refresh rate screens**. Check the example below for a way to do this.

Syntax
------

    window.requestAnimationFrame(callback);

### Parameters

`callback`  
The function to call when it's time to update your animation for the next repaint. The callback function is passed one single argument, a [`DOMHighResTimeStamp`](../domhighrestimestamp) similar to the one returned by [`performance.now()`](../performance/now), indicating the point in time when `requestAnimationFrame()` starts to execute callback functions.

### Return value

A `long` integer value, the request id, that uniquely identifies the entry in the callback list. This is a non-zero value, but you may not make any other assumptions about its value. You can pass this value to [`window.cancelAnimationFrame()`](../window/cancelanimationframe) to cancel the refresh callback request.

Example
-------

In this example, an element is animated for 2 seconds (2000 milliseconds). The element moves at a speed of 0.1px/ms to the right, so its relative position (in CSS pixels) can be calculated in function of the time elapsed since the start of the animation (in milliseconds) with `0.1 * elapsed`. The element's final position is 200px (`0.1 * 2000`) to the right of its initial position.

    const element = document.getElementById('some-element-you-want-to-animate');
    let start;

    function step(timestamp) {
      if (start === undefined)
        start = timestamp;
      const elapsed = timestamp - start;

      // `Math.min()` is used here to make sure that the element stops at exactly 200px.
      element.style.transform = 'translateX(' + Math.min(0.1 * elapsed, 200) + 'px)';

      if (elapsed < 2000) { // Stop the animation after 2 seconds
        window.requestAnimationFrame(step);
      }
    }

    window.requestAnimationFrame(step);

Notes
-----

Edge versions below 17 and Internet Explorer do not reliably fire `requestAnimationFrame` before the paint cycle.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#animation-frames">HTML Living Standard<br />
<span class="small">The definition of 'requestAnimationFrame' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>No change, supersedes the previous one.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/animation-timing/#dom-windowanimationtiming-requestanimationframe">Timing control for script-based animations<br />
<span class="small">The definition of 'requestAnimationFrame' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition</td></tr></tbody></table>

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

`requestAnimationFrame`

24

10

12

23

Callback parameter is a `DOMHighResTimestamp`. This means ten microsecond precision and zero time as `performance.now()`.

11-42

Callback parameter is a `DOMTimestamp`. This means millisecond precision and zero time as `Date.now()`.

4-11

Could be called with no input parameters.

10

15

15

6.1

6

≤37

≤37

25

18

23

14-42

14

14

7

6.1

1.5

1.0

`return_value`

23

12

11

10

15

6.1

≤37

25

14

14

6.1

1.5

See also
--------

-   [`Window.mozAnimationStartTime`](../window/mozanimationstarttime)
-   [`Window.cancelAnimationFrame()`](../window/cancelanimationframe)
-   [mozRequestAnimationFrame](http://weblogs.mozillazine.org/roc/archives/2010/08/mozrequestanima.html) - Blog post
-   [requestAnimationFrame for smart animating](https://paulirish.com/2011/requestanimationframe-for-smart-animating/) - Blog post
-   [Animating with javascript: from setInterval to requestAnimationFrame](https://hacks.mozilla.org/2011/08/animating-with-javascript-from-setinterval-to-requestanimationframe/) - Blog post
-   [Using PC Hardware more efficiently in HTML5: New Web Performance APIs, Part 1](https://blogs.msdn.com/b/ie/archive/2011/07/05/using-pc-hardware-more-efficiently-in-html5-new-web-performance-apis-part-1.aspx) - Blog post
-   [TestUFO: Test your web browser for requestAnimationFrame() Timing Deviations](https://www.testufo.com/#test=animation-time-graph)
-   Paul Irish: [requestAnimationFrame API: now with sub-millisecond precision](http://updates.html5rocks.com/2012/05/requestAnimationFrame-API-now-with-sub-millisecond-precision)
-   [A polyfill](https://github.com/behnammodi/polyfill/blob/master/window.polyfill.js)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/window/requestAnimationFrame" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/window/requestAnimationFrame</a>
