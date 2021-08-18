# CanvasRenderingContext2D.strokeText()

The [`CanvasRenderingContext2D`](../canvasrenderingcontext2d) method `strokeText()`, part of the Canvas 2D API, strokes — that is, draws the outlines of — the characters of a text string at the specified coordinates. An optional parameter allows specifying a maximum width for the rendered text, which the [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) will achieve by condensing the text or by using a lower font size.

This method draws directly to the canvas without modifying the current path, so any subsequent [`fill()`](fill) or [`stroke()`](stroke) calls will have no effect on it.

Use the [`fillText()`](filltext) method to fill the text characters rather than having just their outlines drawn.

## Syntax

    CanvasRenderingContext2D.strokeText(text, x, y [, maxWidth]);

### Parameters

`text`  
A [`DOMString`](../domstring) specifying the text string to render into the context. The text is rendered using the settings specified by [`font`](font), [`textAlign`](textalign), [`textBaseline`](textbaseline), and [`direction`](direction).

`x`  
The x-axis coordinate of the point at which to begin drawing the text.

`y`  
The y-axis coordinate of the point at which to begin drawing the text.

`maxWidth` <span class="badge inline optional">Optional</span>  
The maximum width the text may be once rendered. If not specified, there is no limit to the width of the text. However, if this value is provided, the user agent will adjust the kerning, select a more horizontally condensed font (if one is available or can be generated without loss of quality), or scale down to a smaller font size in order to fit the text in the specified width.

### Return value

[`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined).

## Examples

### Drawing text outlines

This example writes the words "Hello world" using the `strokeText()` method.

#### HTML

First, we need a canvas to draw into. This code creates a context 400 pixels wide and 150 pixels high.

    <canvas id="canvas" width="400" height="150"></canvas>

#### JavaScript

The JavaScript code for this example follows.

    const canvas = document.getElementById('canvas');
    const ctx = canvas.getContext('2d');

    ctx.font = '50px serif';
    ctx.strokeText('Hello world', 50, 90);

This code obtains a reference to the [`<canvas>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/canvas), then gets a reference to its 2D graphics context.

With that in hand, we set the [`font`](font) to 50-pixel-tall "serif" (the user's default [serif](https://en.wikipedia.org/wiki/Serif) font), then call `strokeText()` to draw the text "Hello world," starting at the coordinates (50, 90).

#### Result

### Restricting the text size

This example writes the words "Hello world," restricting its width to 140 pixels.

#### HTML

    <canvas id="canvas" width="400" height="150"></canvas>

#### JavaScript

    const canvas = document.getElementById('canvas');
    const ctx = canvas.getContext('2d');

    ctx.font = '50px serif';
    ctx.strokeText('Hello world', 50, 90, 140);

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/scripting.html#dom-context-2d-stroketext">HTML Living Standard<br />
<span class="small">The definition of 'CanvasRenderingContext2D.strokeText' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`strokeText`

1

12

3.5

9

≤12.1

4

1

18

Yes

≤12.1

3.2

1.0

## See also

- [Drawing text](../canvas_api/tutorial/drawing_text)
- The interface defining this method: [`CanvasRenderingContext2D`](../canvasrenderingcontext2d)
- [`CanvasRenderingContext2D.fillText()`](filltext)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/strokeText" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/strokeText</a>
