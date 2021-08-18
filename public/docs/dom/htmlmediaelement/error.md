HTMLMediaElement.error
======================

The `HTMLMediaElement.error` is the [`MediaError`](../mediaerror) object for the most recent error, or `null` if there has not been an error. When an `error` event is received by the element, you can determine details about what happened by examining this object.

Syntax
------

    var myError = HTMLMediaElement.error;

### Value

A [`MediaError`](../mediaerror) object describing the most recent error to occur on the media element or `null` if no errors have occurred.

Example
-------

This example establishes a video element and adds an error handler to it; the error handler logs the details to console.

    var videoElement = document.createElement('video');
    videoElement.onerror = function() {
      console.log("Error " + videoElement.error.code + "; details: " + videoElement.error.message);
    }
    videoElement.src = "https://example.com/bogusvideo.mp4";

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-media-error">HTML Living Standard<br />
<span class="small">The definition of 'HTMLMediaElement.error' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/embedded-content-0.html#htmlmediaelement">HTML5<br />
<span class="small">The definition of 'HTMLMediaElement.error' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`error`

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
-   [`<audio>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/audio) and [`<video>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/error" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/error</a>
