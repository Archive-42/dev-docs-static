HTMLMediaElement.loop
=====================

The `HTMLMediaElement.loop` property reflects the [`loop`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video#attr-loop) HTML attribute, which controls whether the media element should start over when it reaches the end.

Syntax
------

    var loop = video.loop;
    audio.loop = true;

### Value

A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean).

Example
-------

    var obj = document.createElement('video');
    obj.loop = true; // true

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-media-loop">HTML Living Standard<br />
<span class="small">The definition of 'HTMLMediaElement.loop' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/embedded-content-0.html#htmlmediaelement">HTML5<br />
<span class="small">The definition of 'HTMLMediaElement.loop' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`loop`

3

12

11

9

≤12.1

4

≤37

18

14

≤12.1

3

1.0

See also
--------

-   The interface defining it, [`HTMLMediaElement`](../htmlmediaelement).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/loop" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/loop</a>
