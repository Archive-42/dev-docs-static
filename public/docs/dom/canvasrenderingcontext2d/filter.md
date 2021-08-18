# CanvasRenderingContext2D.filter

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The ` CanvasRenderingContext2D``.filter ` property of the Canvas 2D API provides filter effects such as blurring and grayscaling. It is similar to the CSS [`filter`](https://developer.mozilla.org/en-US/docs/Web/CSS/filter) property and accepts the same values.

## Syntax

    ctx.filter = "<filter-function1> [<filter-function2>] [<filter-functionN>]";
    ctx.filter = "none";

### Values

The `filter` property accepts a value of `"none"` or one or more of the following filter functions in a [`DOMString`](../domstring).

`url()`  
A CSS [`url()`](<https://developer.mozilla.org/en-US/docs/Web/CSS/url()>). Takes an IRI pointing to an SVG filter element, which may be embedded in an external XML file.

`blur()`  
A CSS [`<length>`](https://developer.mozilla.org/en-US/docs/Web/CSS/length). Applies a Gaussian blur to the drawing. It defines the value of the standard deviation to the Gaussian function, i.e., how many pixels on the screen blend into each other; thus, a larger value will create more blur. A value of `0` leaves the input unchanged.

`brightness()`  
A CSS [`<percentage>`](https://developer.mozilla.org/en-US/docs/Web/CSS/percentage). Applies a linear multiplier to the drawing, making it appear brighter or darker. A value under `100%` darkens the image, while a value over `100%` brightens it. A value of `0%` will create an image that is completely black, while a value of `100%` leaves the input unchanged.

`contrast()`  
A CSS [`<percentage>`](https://developer.mozilla.org/en-US/docs/Web/CSS/percentage). Adjusts the contrast of the drawing. A value of `0%` will create a drawing that is completely black. A value of `100%` leaves the drawing unchanged.

`drop-shadow()`  
Applies a drop shadow effect to the drawing. A drop shadow is effectively a blurred, offset version of the drawing's alpha mask drawn in a particular color, composited below the drawing. This function takes up to five arguments:

- `<offset-x>`: See [`<length>`](https://developer.mozilla.org/en-US/docs/Web/CSS/length) for possible units. Specifies the horizontal distance of the shadow.
- `<offset-y>`: See [`<length>`](https://developer.mozilla.org/en-US/docs/Web/CSS/length) for possible units. Specifies the vertical distance of the shadow.
- `<blur-radius>`: The larger this value, the bigger the blur, so the shadow becomes bigger and lighter. Negative values are not allowed.
- `<color>`: See [`<color>`](https://developer.mozilla.org/en-US/docs/Web/CSS/color_value) values for possible keywords and notations.

`grayscale()`  
A CSS [`<percentage>`](https://developer.mozilla.org/en-US/docs/Web/CSS/percentage). Converts the drawing to grayscale. A value of `100%` is completely grayscale. A value of `0%` leaves the drawing unchanged.

`hue-rotate()`  
A CSS [`<angle>`](https://developer.mozilla.org/en-US/docs/Web/CSS/angle). Applies a hue rotation on the drawing. A value of `0deg` leaves the input unchanged.

`invert()`  
A CSS [`<percentage>`](https://developer.mozilla.org/en-US/docs/Web/CSS/percentage). Inverts the drawing. A value of `100%` means complete inversion. A value of `0%` leaves the drawing unchanged.

`opacity()`  
A CSS [`<percentage>`](https://developer.mozilla.org/en-US/docs/Web/CSS/percentage). Applies transparency to the drawing. A value of `0%` means completely transparent. A value of `100%` leaves the drawing unchanged.

`saturate()`  
A CSS [`<percentage>`](https://developer.mozilla.org/en-US/docs/Web/CSS/percentage). Saturates the drawing. A value of `0%` means completely un-saturated. A value of `100%` leaves the drawing unchanged.

`sepia()`  
A CSS [`<percentage>`](https://developer.mozilla.org/en-US/docs/Web/CSS/percentage). Converts the drawing to sepia. A value of `100%` means completely sepia. A value of `0%` leaves the drawing unchanged.

`none`  
No filter is applied. Initial value.

## Examples

To view these examples, make sure to use a browser that supports this feature; see the compatibility table below.

### Applying a blur

This example blurs a piece of text using the `filter` property.

#### HTML

    <canvas id="canvas"></canvas>

#### JavaScript

    const canvas = document.getElementById('canvas');
    const ctx = canvas.getContext('2d');

    ctx.filter = 'blur(4px)';
    ctx.font = '48px serif';
    ctx.fillText('Hello world', 50, 100);

#### Result

### Applying multiple filters

You can combine as many filters as you like. This example applies the `contrast`, `sepia`, and `drop-shadow` filters to a photo of a rhino.

#### HTML

    <canvas id="canvas" width="400" height="150"></canvas>
    <div style="display:none;">
      <img id="source"
           src="https://mdn.mozillademos.org/files/5397/rhino.jpg">
    </div>

#### JavaScript

    const canvas = document.getElementById('canvas');
    const ctx = canvas.getContext('2d');
    const image = document.getElementById('source');

    image.addEventListener('load', e => {
      // Draw unfiltered image
      ctx.drawImage(image, 0, 0, image.width * .6, image.height * .6);

      // Draw image with filter
      ctx.filter = 'contrast(1.4) sepia(1) drop-shadow(-9px 9px 3px #e81)';
      ctx.drawImage(image, 400, 0, -image.width * .6, image.height * .6);
    });

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/scripting.html#filters">HTML Living Standard<br />
<span class="small">The definition of 'CanvasRenderingContext2D.filter' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`filter`

52

79

49

No

39

No

52

52

49

41

No

6.0

## See also

- The interface defining this property: [`CanvasRenderingContext2D`](../canvasrenderingcontext2d)
- CSS [`filter`](https://developer.mozilla.org/en-US/docs/Web/CSS/filter)
- CSS [`<filter-function>`](https://developer.mozilla.org/en-US/docs/Web/CSS/filter-function)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/filter" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/filter</a>
