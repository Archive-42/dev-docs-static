# CanvasRenderingContext2D.clearHitRegions()

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The [`CanvasRenderingContext2D`](../canvasrenderingcontext2d) method `clearHitRegions()` removes all hit regions from the canvas.

## Syntax

    void ctx.clearHitRegions();

## Examples

### Using the `clearHitRegions` method

This example demonstrates the `clearHitRegions()` method.

#### HTML

    <canvas id="canvas"></canvas>

#### JavaScript

    const canvas = document.getElementById('canvas');
    const ctx = canvas.getContext('2d');

    // Set some hit regions
    ctx.addHitRegion({id: 'eyes'});
    ctx.addHitRegion({id: 'nose'});
    ctx.addHitRegion({id: 'mouth'});

    // Remove them altogether from the canvas
    ctx.clearHitRegions();

## Specifications

Canvas hit regions have been removed from the WHATWG Living Standard, although discussions about future standardization are ongoing. See <https://github.com/whatwg/html/issues/3407> for more information.

## Browser compatibility

No compatibility data found for `api.CanvasRenderingContext2D.clearHitRegions`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

## See also

- [`CanvasRenderingContext2D.addHitRegion()`](addhitregion) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>
- [`CanvasRenderingContext2D.removeHitRegion()`](removehitregion) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/clearHitRegions" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/clearHitRegions</a>
