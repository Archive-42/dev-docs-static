HTMLMediaElement.controls
=========================

The `HTMLMediaElement.controls` property reflects the [`controls`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video#attr-controls) HTML attribute, which controls whether user interface controls for playing the media item will be displayed.

Syntax
------

    var ctrls = video.controls;
    audio.controls = true;

### Value

A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean). A value of `true` means controls will be displayed.

Example
-------

    var obj = document.createElement('video');
    obj.controls = true;

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-media-controls">HTML Living Standard<br />
<span class="small">The definition of 'HTMLMediaElement.controls' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>No change from <a href="https://www.w3.org/TR/html52/">HTML5</a></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/embedded-content-0.html#htmlmediaelement">HTML5<br />
<span class="small">The definition of 'HTMLMediaElement.controls' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`controls`

43

12

3.5

9

≤12.1

3.2

43

43

4

≤12.1

3

4.0

See also
--------

-   The interface defining it, [`HTMLMediaElement`](../htmlmediaelement).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/controls" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/controls</a>
