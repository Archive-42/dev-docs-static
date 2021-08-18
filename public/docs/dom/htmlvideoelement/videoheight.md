HTMLVideoElement.videoHeight
============================

The [`HTMLVideoElement`](../htmlvideoelement) interface's read-only `videoHeight` property indicates the **intrinsic height** of the video, expressed in CSS pixels. In simple terms, this is the height of the media in its natural size. See [About intrinsic width and height](#about_intrinsic_width_and%0A__height) for more details.

Syntax
------

    height = htmlVideoElement.videoHeight;

### Value

An integer value specifying the intrinsic height of the video in CSS pixels. If the element's [`readyState`](../htmlmediaelement/readystate) is `HTMLMediaElement.HAVE_NOTHING`, then the value of this property is 0, because neither video nor poster frame size information is yet available.

### About intrinsic width and height

A [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) calculates the intrinsic width and height of the element's media by starting with the media's raw pixel width and height, then taking into account factors including:

-   The media's aspect ratio.
-   The media's clean aperture (the sub-rectangle centered within the media that matches the target aspect ratio).
-   The target device's resolution.
-   Any other factors required by the media format.

If the element is currently displaying the poster frame rather than rendered video, the poster frame's intrinsic size is considered to be the size of the `<video>` element.

If at any time the intrinsic size of the media changes and the element's [`readyState`](../htmlmediaelement/readystate) isn't `HAVE_NOTHING`, a <span class="page-not-created">`resize`</span> event will be sent to the `<video>` element. This can happen when the element switches from displaying the poster frame to displaying video content, or when the displayed video track changes.

Example
-------

This example creates a handler for the <span class="page-not-created">`resize`</span> event that resizes the [`<video>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video) element to match the intrinsic size of its contents.

    let v = document.getElementById("myVideo");

    v.addEventListener("resize", ev => {
      let w = v.videoWidth;
      let h = v.videoHeight;

      if (w && h) {
        v.style.width = w;
        v.style.height = h;
      }
    }, false);

Note that this only applies the change if both the `videoWidth` and the `videoHeight` are non-zero. This avoids applying invalid changes when there's no true information available yet for dimensions.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-video-videoheight">HTML Living Standard<br />
<span class="small">The definition of 'HTMLVideoElement.videoHeight' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/semantics-embedded-content.html#dom-htmlvideoelement-videoheight">HTML5<br />
<span class="small">The definition of 'HTMLVideoElement.videoHeight' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`videoHeight`

1

12

3.5

9

10.5

3.1

1

18

4

11

2

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLVideoElement/videoHeight" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLVideoElement/videoHeight</a>
