# CanvasGradient.addColorStop()

The ` CanvasGradient``.addColorStop() ` method adds a new color stop, defined by an `offset` and a `color`, to a given canvas gradient.

## Syntax

    void gradient.addColorStop(offset, color);

### Parameters

`offset`  
A number between `0` and `1`, inclusive, representing the position of the color stop. `0` represents the start of the gradient and `1` represents the end; an `INDEX_SIZE_ERR` is raised if the number is outside that range.

`color`  
A [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [`<color>`](https://developer.mozilla.org/en-US/docs/Web/CSS/color_value) value representing the color of the stop. A `SYNTAX_ERR` is raised if the value cannot be parsed as a CSS `<color>` value.

## Examples

### Adding stops to a gradient

This example uses the `addColorStop` method to add stops to a linear [`CanvasGradient`](../canvasgradient) object. The gradient is then used to fill a rectangle.

#### HTML

    <canvas id="canvas"></canvas>

#### JavaScript

    const canvas = document.getElementById('canvas');
    const ctx = canvas.getContext('2d');

    let gradient = ctx.createLinearGradient(0, 0, 200, 0);
    gradient.addColorStop(0, 'green');
    gradient.addColorStop(.7, 'white');
    gradient.addColorStop(1, 'pink');
    ctx.fillStyle = gradient;
    ctx.fillRect(10, 10, 200, 100);

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/scripting.html#dom-canvasgradient-addcolorstop">HTML Living Standard<br />
<span class="small">The definition of 'CanvasGradient.addColorStop' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`addColorStop`

6

12

3.6

9

9

5.1

≤37

18

4

10.1

6

1.0

## See also

- The interface defining this method: [`CanvasGradient`](../canvasgradient)
- [`CanvasRenderingContext2D.createLinearGradient()`](../canvasrenderingcontext2d/createlineargradient)
- [`CanvasRenderingContext2D.createRadialGradient()`](../canvasrenderingcontext2d/createradialgradient)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CanvasGradient/addColorStop" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CanvasGradient/addColorStop</a>
