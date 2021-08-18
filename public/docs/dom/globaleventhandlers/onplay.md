GlobalEventHandlers.onplay
==========================

The `onplay` property of the [`GlobalEventHandlers`](../globaleventhandlers) mixin is the [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) for processing `play` events.

Syntax
------

    element.onplay = handlerFunction;
    var handlerFunction = element.onplay;

`handlerFunction` should be either `null` or a [JavaScript function](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions) specifying the handler for the event.

Example
-------

    <p>This example demonstrates how to assign an "onplay" event to a video element.</p>

    <video controls onplay="alertPlay()">
      <source src="mov_bbb.mp4" type="video/mp4">
      <source src="mov_bbb.ogg" type="video/ogg">
      Your browser does not support HTML5 video.
    </video>

    <p>Video courtesy of <a href="http://www.bigbuckbunny.org/" target="_blank">Big Buck Bunny</a>.</p>

    <script>
    function alertPlay() {
      alert("The video has started to play.");
    }
    </script>

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/webappapis.html#handler-onplay">HTML Living Standard<br />
<span class="small">The definition of 'onplay' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`onplay`

32

12

9

9

19

≤12.1-15

9

4.4.3

32

9

19

≤12.1-14

9

2.0

See also
--------

-   `play`
-   [Information on working with event handlers](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onplay" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onplay</a>
