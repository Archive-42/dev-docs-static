# HTMLImageElement.width

The `width` property of the [`HTMLImageElement`](../htmlimageelement) interface indicates the width at which an image is drawn in [CSS pixels](https://developer.mozilla.org/en-US/docs/Glossary/CSS_pixel) if it's being drawn or rendered to any visual medium such as a screen or printer. Otherwise, it's the natural, pixel density-corrected width of the image.

## Syntax

    htmlImageElement.width = newWidth;
    let width = htmlImageElement.width;

### Value

An integer value indicating the width of the image. The way the width is defined depends on whether or not the image is being rendered to a visual medium, such as a screen or printer:

- If the image is being rendered to a visual medium, the width is expressed in [CSS pixels](https://developer.mozilla.org/en-US/docs/Glossary/CSS_pixel).
- If the image is not being rendered to a visual medium, its width is represented using the image's natural (intrinsic) width, adjusted for the display density as indicated by [`naturalWidth`](naturalwidth).

## Example

In this example, two different sizes are provided for an image of a clock using the [`srcset`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img#attr-srcset) attribute. One is 200px wide and the other is 400px wide. The [`sizes`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img#attr-sizes) attribute is used to specify the width at which the image should be drawn given the viewport's width.

### HTML

For viewports up to 400px wide, the image is drawn at a width of 200px. Otherwise, it's drawn at 400px.

    <p>Image width: <span class="size">?</span>px (resize to update)</p>
    <img src="/files/16864/clock-demo-200px.png"
          alt="Clock"
          srcset="/files/16864/clock-demo-200px.png 200w,
              /files/16797/clock-demo-400px.png 400w"
          sizes="(max-width: 400px) 200px, 400px">

### JavaScript

JavaScript looks at the `width` property to determine the width of the image at the moment. This is performed in the window's [`load`](../window/load_event) and [`resize`](../window/resize_event) event handlers so the most current width information is always available.

    var clockImage = document.querySelector("img");
    let output = document.querySelector(".size");

    const updateWidth = event => { output.innerText = clockImage.width; };

    window.addEventListener("load", updateWidth);
    window.addEventListener("resize", updateWidth);

### Result

This example may be easier to try out [in its own window](https://yari-demos.prod.mdn.mozit.cloud/en-US/docs/Web/API/HTMLImageElement/width/_samples_/Example).

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-img-width">HTML Living Standard<br />
<span class="small">The definition of 'HTMLImageElement.width' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`width`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLImageElement/width" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLImageElement/width</a>
