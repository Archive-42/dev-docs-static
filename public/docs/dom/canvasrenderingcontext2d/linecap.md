# CanvasRenderingContext2D.lineCap

The ` CanvasRenderingContext2D``.lineCap ` property of the Canvas 2D API determines the shape used to draw the end points of lines.

**Note:** Lines can be drawn with the [`stroke()`](stroke), [`strokeRect()`](strokerect), and [`strokeText()`](stroketext) methods.

## Syntax

    ctx.lineCap = "butt" || "round" || "square";

### Options

`"butt"`  
The ends of lines are squared off at the endpoints. Default value.

`"round"`  
The ends of lines are rounded.

`"square"`  
The ends of lines are squared off by adding a box with an equal width and half the height of the line's thickness.

## Examples

### Changing the shape of line caps

This example rounds the end caps of a straight line.

#### HTML

    <canvas id="canvas"></canvas>

#### JavaScript

    const canvas = document.getElementById('canvas');
    const ctx = canvas.getContext('2d');

    ctx.beginPath();
    ctx.moveTo(20, 20);
    ctx.lineWidth = 15;
    ctx.lineCap = 'round';
    ctx.lineTo(100, 100);
    ctx.stroke();

#### Result

### Comparison of line caps

In this example three lines are drawn, each with a different value for the `lineCap` property. Two guides to see the exact differences between the three are added. Each of these lines starts and ends exactly on these guides.

The line on the left uses the default `"butt"` option. It's drawn completely flush with the guides. The second is set to use the `"round"` option. This adds a semicircle to the end that has a radius half the width of the line. The line on the right uses the `"square"` option. This adds a box with an equal width and half the height of the line thickness.

    const canvas = document.getElementById('canvas');
    const ctx = canvas.getContext('2d');
    const lineCap = ['butt', 'round', 'square'];

    // Draw guides
    ctx.strokeStyle = '#09f';
    ctx.beginPath();
    ctx.moveTo(10, 10);
    ctx.lineTo(140, 10);
    ctx.moveTo(10, 140);
    ctx.lineTo(140, 140);
    ctx.stroke();

    // Draw lines
    ctx.strokeStyle = 'black';
    for (let i = 0; i < lineCap.length; i++) {
      ctx.lineWidth = 15;
      ctx.lineCap = lineCap[i];
      ctx.beginPath();
      ctx.moveTo(25 + i * 50, 10);
      ctx.lineTo(25 + i * 50, 140);
      ctx.stroke();
    }

<table><thead><tr class="header"><th>Screenshot</th><th>Live sample</th></tr></thead><tbody><tr class="odd"><td><img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAL4AAAC+CAMAAAC8qkWvAAAAGXRFWHRTb2Z0d2FyZQBBZG9iZSBJbWFnZVJlYWR5ccllPAAAAD9QTFRF9/f3////zMzMhoaG+vr6+Pj4AAAA/f39/Pz8/v7+d3d3h87/dsn/7Ozs3d3dQWiDdnZ2vLy8IiIiCwsLlJSUdGB7kwAAAn9JREFUeNrt3eFSqzAQhuGkgkLtRmi9/2s9PVXHEtkmKYEm03cZRxnZ+PAR9I8za2zVZeDDhw8fPvxK+a24XeHlpFX4vXFOTOElzpl5fls+/usG2jl+L85UUU5m07+EX/jH5ZOb5e/qCF/Mrma+uc0vdesYCfOl9I0TTL9kuInhXz0qKeHcv4/I9KWUc5meh/e+5EOkrmeC37+dvsQsEjj/fvTj5+coJm693cukxtkGSXp15fZT1M6/T4bT67lOg0Td9MvrpPb6k4njL9yq7vgjOTrvepk7n+PP/6gtfnHK8ZdyjPlzcotvNufvIy1l8uV0bTlJZfxxihkfw3+/tz6mmI+7OxbxD1/lL30IVraOHJvHe7BD8lbI2rGUv8+5kzd4deHDhw8fPnz48OEXwm/V8pdug7VmB3z48OHDhw8fPnz48OHXxm+U4+/STeBYs0PjN9HJNMlZZuwgfdInfdInfdInfdIn/VrTb9Tyl26CtWYHfPjw4cOHDx8+fPjwn5DfKcffpbvAsWaHxu+ik+mSs8zYQfqkT/qkT/qkT/qk/8Tpd2r5S3fBWrMDPnz48OHDhw8fPnz46fw3tfyl34K1Zgd8+PDhw4cPHz58+PCfjt+r5S/dB2vNDvjw4cOHDx8+fPjw4Wfh555lkN6xiH+4t7JNP8ixeZLL+qMzkjfPkHHvp5c/uOShr+4dtU98c5fzs07/nA7tiWjw+fqVW/Dt9cgkWx/f/g6ssjXyzzdwGRcWefE4TGp8PH9J9XXzLXz42/GbOvTK/+87qYOvjAcWVwdfGc7c1hG/Mhr7/LVzUvj+b/TB5Laveiz8/xvoi987U6GxVRd8+PDhw38u/j9+9zvAu5qbDwAAAABJRU5ErkJggg==" class="internal" /></td><td></td></tr></tbody></table>

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/scripting.html#dom-context-2d-linecap">HTML Living Standard<br />
<span class="small">The definition of 'CanvasRenderingContext2D.lineCap' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`lineCap`

1

12

1.5

9

≤12.1

2

1

18

4

≤12.1

1

1.0

### WebKit/Blink-specific notes

- In WebKit- and Blink-based Browsers, a non-standard and deprecated method `ctx.setLineCap()` is implemented in addition to this property.

## See also

- The interface defining this property: [`CanvasRenderingContext2D`](../canvasrenderingcontext2d)
- [`CanvasRenderingContext2D.lineWidth`](linewidth)
- [`CanvasRenderingContext2D.lineJoin`](linejoin)
- [Applying styles and color](../canvas_api/tutorial/applying_styles_and_colors)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/lineCap" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/lineCap</a>
