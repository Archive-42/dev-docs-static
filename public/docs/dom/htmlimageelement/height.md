# HTMLImageElement.height

The `height` property of the [`HTMLImageElement`](../htmlimageelement) interface indicates the height at which the image is drawn, in <span class="page-not-created">CSS pixels</span> if the image is being drawn or rendered to any visual medium such as the screen or a printer; otherwise, it's the natural, pixel density corrected height of the image.

## Syntax

    htmlImageElement.height = newHeight;
    let height = htmlImageElement.height;

### Value

An integer value indicating the height of the image. The terms in which the height is defined depends on whether the image is being rendered to a visual medium or not.

- If the image is being rendered to a visual medium such as a screen or printer, the height is expressed in <span class="page-not-created">CSS pixels</span>.
- Otherwise, the image's height is represented using its natural (intrinsic) height, adjusted for the display density as indicated by [`naturalHeight`](naturalheight).

## Example

In this example, two different sizes are provided for an image of a clock using the [`srcset`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img#attr-srcset) attribute. One is 200px wide and the other is 400px wide. Further, the [`sizes`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img#attr-sizes) attribute is provided to specify the width at which the image should be drawn given the viewport's width.

### HTML

Specifically, for viewports up to 400px wide, the image is drawn at a width of 200px; otherwise, it's drawn at 300px.

    <p>Image height: <span class="size">?</span>px (resize to update)</p>
    <img src="/files/17373/clock-demo-200px.png"
          alt="Clock"
          srcset="/files/17373/clock-demo-200px.png 200w,
              /files/17374/clock-demo-400px.png 400w"
          sizes="(max-width: 400px) 200px, 300px">

### JavaScript

The JavaScript code looks at the `height` to determine the height of the image given the width at which it's currently drawn.

    var clockImage = document.querySelector("img");
    let output = document.querySelector(".size");

    const updateHeight = event => { output.innerText = clockImage.height; };

    window.addEventListener("load", updateHeight);
    window.addEventListener("resize", updateHeight);

### Result

This example may be easier to try out [in its own window](https://yari-demos.prod.mdn.mozit.cloud/en-US/docs/Web/API/HTMLImageElement/height/_samples_/Example).

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-img-height">HTML Living Standard<br />
<span class="small">The definition of 'HTMLImageElement.height' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

## Browser compatibility

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

`height`

1

12

1

5.5

≤12.1

3

1

Yes

4

≤12.1

1

Yes

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLImageElement/height" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLImageElement/height</a>
