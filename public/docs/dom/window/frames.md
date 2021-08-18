Window.frames
=============

Returns the window itself, which is an array-like object, listing the direct sub-frames of the current window.

Syntax
------

    frameList = window.frames;

-   `frameList` is a list of frame objects. It is similar to an array in that it has a `length` property and its items can be accessed using the `[i]` notation.
-   `frameList === window` evaluates to true.
-   Each item in the window.frames pseudo-array represents the [`Window`](../window) object corresponding to the given [`<frame>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/frame)'s or [`<iframe>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe)'s content, not the (i)frame DOM element (i.e., `window.frames[0]` is the same thing as `document.getElementsByTagName("iframe")[0].contentWindow`).
-   For more details about the returned value, refer to this [thread on mozilla.dev.platform](https://groups.google.com/group/mozilla.dev.platform/browse_thread/thread/5628c6f346859d4f/169aa7004565066?hl=en&ie=UTF-8&oe=utf-8&q=window.frames&pli=1).

Example
-------

    var frames = window.frames; // or // var frames = window.parent.frames;
    for (var i = 0; i < frames.length; i++) {
      // do something with each subframe as frames[i]
      frames[i].document.body.style.background = "red";
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/browsers.html#dom-frames">HTML Living Standard<br />
<span class="small">The definition of 'Window.frames' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/browsers.html#dom-frames">HTML5<br />
<span class="small">The definition of 'Window.frames' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`frames`

1

12

1

4

≤12.1

1

1

18

4

≤12.1

1

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Window/frames" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Window/frames</a>
