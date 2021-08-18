# CanvasRenderingContext2D.imageSmoothingQuality

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `imageSmoothingQuality` property of the [`CanvasRenderingContext2D`](../canvasrenderingcontext2d) interface, part of the [Canvas API](../canvas_api), lets you set the quality of image smoothing.

**Note:** For this property to have an effect, [`imageSmoothingEnabled`](imagesmoothingenabled) must be `true`.

## Syntax

    ctx.imageSmoothingQuality = "low" || "medium" || "high"

### Options

Possible values:

`"low"`  
Low quality.

`"medium"`  
Medium quality.

`"high"`  
High quality.

## Example

### Setting image smoothing quality

This example uses the `imageSmoothingQuality` property with a scaled image.

#### HTML

    <canvas id="canvas"></canvas>

#### JavaScript

    const canvas = document.getElementById('canvas');
    const ctx = canvas.getContext('2d');

    let img = new Image();
    img.src = 'https://mdn.mozillademos.org/files/222/Canvas_createpattern.png';
    img.onload = function() {
      ctx.imageSmoothingQuality = 'low';
      ctx.drawImage(img, 0, 0, 300, 150);
    };

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#imagesmoothingquality">HTML Living Standard<br />
<span class="small">The definition of 'imageSmoothingQuality' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`imageSmoothingQuality`

54

79

No

No

41

9.1

54

54

No

41

9.3

6.0

## See also

- The interface defining this property: [`CanvasRenderingContext2D`](../canvasrenderingcontext2d)
- [`CanvasRenderingContext2D.imageSmoothingEnabled`](imagesmoothingenabled)
- [`image-rendering`](https://developer.mozilla.org/en-US/docs/Web/CSS/image-rendering)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/imageSmoothingQuality" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/imageSmoothingQuality</a>
