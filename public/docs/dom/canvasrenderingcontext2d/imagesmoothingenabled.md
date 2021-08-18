# CanvasRenderingContext2D.imageSmoothingEnabled

The `imageSmoothingEnabled` property of the [`CanvasRenderingContext2D`](../canvasrenderingcontext2d) interface, part of the [Canvas API](../canvas_api), determines whether scaled images are smoothed (`true`, default) or not (`false`). On getting the `imageSmoothingEnabled` property, the last value it was set to is returned.

This property is useful for games and other apps that use pixel art. When enlarging images, the default resizing algorithm will blur the pixels. Set this property to `false` to retain the pixels' sharpness.

**Note:** You can adjust the smoothing quality with the [`imageSmoothingQuality`](imagesmoothingquality) property.

## Syntax

    ctx.imageSmoothingEnabled = value;

### Options

`value`  
A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) indicating whether to smooth scaled images or not. The default value is `true`.

## Examples

### Disabling image smoothing

This example compares three images. The first image is drawn at its natural size, the second is scaled to 3X and drawn with image smoothing enabled, and the third is scaled to 3X but drawn with image smoothing disabled.

#### HTML

    <canvas id="canvas" width="460" height="210"></canvas>

#### JavaScript

    const canvas = document.getElementById('canvas');

    const ctx = canvas.getContext('2d');
    ctx.font = '16px sans-serif';
    ctx.textAlign = 'center';

    const img = new Image();
    img.src = 'https://interactive-examples.mdn.mozilla.net/media/examples/star.png';
    img.onload = function() {
      const w = img.width,
            h = img.height;

      ctx.fillText('Source', w * .5, 20);
      ctx.drawImage(img, 0, 24, w, h);

      ctx.fillText('Smoothing = TRUE', w * 2.5, 20);
      ctx.imageSmoothingEnabled = true;
      ctx.drawImage(img, w, 24, w * 3, h * 3);

      ctx.fillText('Smoothing = FALSE', w * 5.5, 20);
      ctx.imageSmoothingEnabled = false;
      ctx.drawImage(img, w * 4, 24, w * 3, h * 3);
    };

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/scripting.html#dom-context-2d-imagesmoothingenabled">HTML Living Standard<br />
<span class="small">The definition of 'CanvasRenderingContext2D.imageSmoothingEnabled' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`imageSmoothingEnabled`

30

21-30

15

51

Yes-51

Yes

17

15-17

9.1

4.4

30

25-30

51

Yes-51

18

14-18

9.3

2.0

1.5-2.0

## See also

- The interface defining this property: [`CanvasRenderingContext2D`](../canvasrenderingcontext2d)
- [`CanvasRenderingContext2D.imageSmoothingQuality`](imagesmoothingquality)
- [`image-rendering`](https://developer.mozilla.org/en-US/docs/Web/CSS/image-rendering)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/imageSmoothingEnabled" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/imageSmoothingEnabled</a>
