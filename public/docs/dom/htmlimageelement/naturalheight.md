# HTMLImageElement.naturalHeight

The [`HTMLImageElement`](../htmlimageelement) interface's `naturalHeight` property is a read-only value which returns the intrinsic (natural), density-corrected height of the image in [CSS pixels](https://developer.mozilla.org/en-US/docs/Glossary/CSS_pixel). This is the height the image is if drawn with nothing constraining its height; if you don't specify a height for the image, or place the image inside a container that either limits or expressly specifies the image height, it will be rendered this tall.

## Syntax

    let naturalHeight = htmlImageElement.naturalHeight;

### Value

An integer value indicating the intrinsic height, in CSS pixels, of the image. This is the height at which the image is naturally drawn when no constraint or specific value is established for the image. This natural height is corrected for the pixel density of the device on which it's being presented, unlike [`height`](height).

If the intrinsic height is not available—either because the image does not specify an intrinsic height or because the image data is not available in order to obtain this information, `naturalHeight` returns 0.

## Example

This example displays both the natural, density-adjusted size of an image as well as its rendered size as altered by the page's CSS and other factors.

### HTML

    <div class="box">
      <img src="/files/16797/clock-demo-400px.png" class="image">
    </div>
    <div class="output">
    </div>

The HTML features a 400x398 pixel image which is placed inside a [`<div>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/div).

### CSS

    .box {
      width: 200px;
      height: 200px;
    }

    .image {
      width: 100%;
    }

    .output {
      padding-top: 2em;
    }

The main thing of note in the CSS above is that the style used for the container the image will be drawn in is 200px wide, and the image will be drawn to fill its width (100%).

### JavaScript

    let output = document.querySelector(".output");
    let image = document.querySelector("img");

    window.addEventListener("load", event => {
      output.innerHTML += `Natural size: ${image.naturalWidth} x ` +
                          `${image.naturalHeight} pixels<br>`;
      output.innerHTML += `Displayed size: ${image.width} x ` +
                          `${image.height} pixels`;
    });

The JavaScript code dumps the natural and as-displayed sizes into the [`<div>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/div) with the class `output`. This is done in response to the window's [`load`](../window/load_event) event handler, in order to ensure that the image is available before attempting to examine its width and height.

### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-img-naturalheight">HTML Living Standard<br />
<span class="small">The definition of 'HTMLImageElement.naturalheight' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`naturalHeight`

1

12

1

9

≤12.1

3

1

Yes

4

≤12.1

1

Yes

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLImageElement/naturalHeight" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLImageElement/naturalHeight</a>
