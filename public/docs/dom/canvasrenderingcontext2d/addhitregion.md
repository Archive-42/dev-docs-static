# CanvasRenderingContext2D.addHitRegion()

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The [`CanvasRenderingContext2D`](../canvasrenderingcontext2d) method `addHitRegion()` adds a hit region to the bitmap.

Canvas hit regions make hit detection easy. They let you route events to DOM elements, and make it possible for users to explore the canvas without seeing it.

## Syntax

    void ctx.addHitRegion(options);

### Options

The `options` argument is optional. When provided, it is an [`Object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object) which can contain the following properties:

`path`  
A [`Path2D`](../path2d) object describing the area of the hit region. If not provided, the current path is used.

`fillRule`  
The algorithm by which to determine if a point is inside or outside the hit region.  
Possible values:

- `nonzero`: The [non-zero winding rule](https://en.wikipedia.org/wiki/Nonzero-rule). Default rule.
- `evenodd`: The [even-odd winding rule](https://en.wikipedia.org/wiki/Even%E2%80%93odd_rule).

`id`  
The ID for this hit region to reference it for later use in events, for example.

`parentID`  
The ID of the parent region for cursor fallback and navigation by accessibility tools.

`cursor`  
The [`cursor`](https://developer.mozilla.org/en-US/docs/Web/CSS/cursor) to use when the mouse is over this region (defaults to `inherit`). Inherits the cursor of the parent hit region, if any, or the canvas element's cursor.

`control`  
An element (descendant of the canvas) to which events are to be routed. Defaults to `null`.

`label`  
A text label for accessibility tools to use as a description of the region, if there is no control. Defaults to `null`.

`role`  
An [ARIA role](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA) for accessibility tools to determine how to represent this region, if there is no control. Defaults to `null`.

## Examples

### Using the `addHitRegion` method

This example demonstrates the `addHitRegion()` method.

#### HTML

    <canvas id="canvas"></canvas>

#### JavaScript

    const canvas = document.getElementById('canvas');
    const ctx = canvas.getContext('2d');

    canvas.addEventListener('mousemove', function(event) {
      if(event.region) {
        alert('ouch, my eye :(');
      }
    });

    ctx.beginPath();
    ctx.arc(100, 100, 75, 0, 2 * Math.PI);
    ctx.lineWidth = 5;
    ctx.stroke();

    // Eyes
    ctx.beginPath();
    ctx.arc(70, 80, 10, 0, 2 * Math.PI);
    ctx.arc(130, 80, 10, 0, 2 * Math.PI);
    ctx.fill();
    ctx.addHitRegion({id: "eyes"});

    // Mouth
    ctx.beginPath();
    ctx.arc(100, 110, 50, 0, Math.PI);
    ctx.stroke();

Edit the code below to see your changes update live in the canvas. (If you don't see the full smiley, check the browser compatibility table to see if your current browser supports hit regions already; you might need to activate a preference.)

## Specifications

Canvas hit regions have been removed from the WHATWG Living Standard, although discussions about future standardization are ongoing. See <https://github.com/whatwg/html/issues/3407> for more information.

## Browser compatibility

No compatibility data found for `api.CanvasRenderingContext2D.addHitRegion`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

## See also

- [`CanvasRenderingContext2D.removeHitRegion()`](removehitregion) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>
- [`CanvasRenderingContext2D.clearHitRegions()`](clearhitregions) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/addHitRegion" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/addHitRegion</a>
