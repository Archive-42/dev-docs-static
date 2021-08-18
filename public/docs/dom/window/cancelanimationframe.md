window.cancelAnimationFrame()
=============================

The `window.cancelAnimationFrame()` method cancels an animation frame request previously scheduled through a call to [`window.requestAnimationFrame()`](../window/requestanimationframe).

Syntax
------

    window.cancelAnimationFrame(requestID);

### Parameters

`requestID`  
The ID value returned by the call to [`window.requestAnimationFrame()`](../window/requestanimationframe) that requested the callback.

Examples
--------

    var requestAnimationFrame = window.requestAnimationFrame || window.mozRequestAnimationFrame ||
                                window.webkitRequestAnimationFrame || window.msRequestAnimationFrame;

    var cancelAnimationFrame = window.cancelAnimationFrame || window.mozCancelAnimationFrame;

    var start = window.mozAnimationStartTime;  // Only supported in FF. Other browsers can use something like Date.now().

    var myReq;

    function step(timestamp) {
      var progress = timestamp - start;
      d.style.left = Math.min(progress / 10, 200) + 'px';
      if (progress < 2000) {
        // it's important to update the requestId each time you're calling requestAnimationFrame
        myReq = requestAnimationFrame(step);
      }
    }
    myReq = requestAnimationFrame(step);
    // the cancelation uses the last requestId
    cancelAnimationFrame(myReq);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#animationframeprovider-cancelanimationframe">HTML Living Standard<br />
<span class="small">The definition of 'cancelAnimationFrame()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`cancelAnimationFrame`

24

12

23

11-23

10

15

6.1

6-6.1

≤37

25

23

14-23

14

7

1.5

See also
--------

-   [`window.mozAnimationStartTime`](mozanimationstarttime)
-   [`window.requestAnimationFrame()`](../window/requestanimationframe)
-   [A polyfill](https://github.com/behnammodi/polyfill/blob/master/window.polyfill.js)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Window/cancelAnimationFrame" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Window/cancelAnimationFrame</a>
