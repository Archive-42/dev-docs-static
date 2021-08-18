# CanvasRenderingContext2D.restore()

The ` CanvasRenderingContext2D``.restore() ` method of the Canvas 2D API restores the most recently saved canvas state by popping the top entry in the drawing state stack. If there is no saved state, this method does nothing.

For more information about the [drawing state](save#drawing_state), see [`CanvasRenderingContext2D.save()`](save).

## Syntax

    void ctx.restore();

## Examples

### Restoring a saved state

This example uses the `save()` method to save the default state and `restore()` to restore it later, so that you are able to draw a rect with the default state later.

#### HTML

    <canvas id="canvas"></canvas>

#### JavaScript

    const canvas = document.getElementById('canvas');
    const ctx = canvas.getContext('2d');

    // Save the default state
    ctx.save();

    ctx.fillStyle = 'green';
    ctx.fillRect(10, 10, 100, 100);

    // Restore the default state
    ctx.restore();

    ctx.fillRect(150, 40, 100, 100);

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/scripting.html#dom-context-2d-restore">HTML Living Standard<br />
<span class="small">The definition of 'CanvasRenderingContext2D.restore' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`restore`

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

## See also

- The interface defining this method: [`CanvasRenderingContext2D`](../canvasrenderingcontext2d)
- [`CanvasRenderingContext2D.save()`](save)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/restore" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/restore</a>
