# CanvasRenderingContext2D.translate()

The ` CanvasRenderingContext2D``.translate() ` method of the Canvas 2D API adds a translation transformation to the current matrix.

## Syntax

    void ctx.translate(x, y);

The `translate()` method adds a translation transformation to the current matrix by moving the canvas and its origin `x` units horizontally and `y` units vertically on the grid.

<img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAANwAAADcCAMAAAAshD+zAAAAGXRFWHRTb2Z0d2FyZQBBZG9iZSBJbWFnZVJlYWR5ccllPAAAAGlQTFRF9vb2/Pz8+fn5+vr69/f3/f39+Pj4/v7+////5eXl+/v7zMzMAAAA5jUApqamz8/P6urqurq6SUlJ+M/CYWFh29vbfHx88fHxMzMz7W5I8puB4ODg++3pk5OT8IZmFhYW9bWhrq6u61ouTLUuRwAAA8JJREFUeNrt3etyqjAUBWCKKEFAAiTc8fb+D3mirR174HiIBU32rDVDfiBN+WYnxDJ0cBjhOMABBxxwwAEHHAGcy2USWpxEcvcfON+RLS8de+OVvJXOOM6VgWN9AumO4njrEEjLR3GSU8BxOYpLSgI2r0xGcaFDIiFw6tKTVVlAFZeFTpgRxQUXmHWlm4hLC9UUKVGcUI0ginOqr40krhep6Mmuc6l1M24Czp4FLlAjKw21cPYscF4WBlUwAefdwjPVZNyzIbIq+h87/oNTU021RaqayFhUdDu1IvN0cF4qVCPSSw9G53qyotLDedXX5kXfnwYjd5fG9sUTj4smHjeyb3dfuTTrCz3cdYEzG/ddB+lVXAe38dLrjFsQpwbVHLjNrlCXCKFVOc+5TVvDcV9EVwvnLY2bbVgOAhxwwBmLC25JgmHG9sUTj4smHjeyD5UDDjjggAMOOOCAA446rk0YK9N34DbDzI47lKwQv8VtHuV9OF8U7NASxanS9RmjivNFlJLFsV3G6FauOpmDm/seyukwwz0UUytXnBjdYTnLNxTggAMOOOCAA25OXFfXdUcVV+csr4ninPoC7IzFucNMx+WNapr8JTj3URbB7VWzJ4pj58/tFU8Q3Z1gd3TdPF8cd9zn++PLcW6dd3W3OE7NuvxF69z9GXZ1c1x+WGou4sEvcXF8PUHPaeqn51xscq6nuD+7ZCuX101DDvd9Qencc0cTtzo2qnh7opVbqW1Ddli+5hsKcMABBxxwBHCrYczErR4FOOCAAw64mXGL/S/PL/ahcsABBxxwwAEHHBHcdphRnF+eSpYm78NtH+WXOMaESA5UcX5ZRTtGtXJ+fyjJ4k4HUVHFXSZcJsjOOcboDss3r3Mz4j6f9Znyiy9H2oTTzUvuoaBymHPAAQcccE/gPoYxE/fxKMABBxxwwAEHHHDAmYoz8jkUVA444IADbincehgzcetHAQ444IADDjjggAMOuDfgjLyHgsoBBxxwwAH3BM4fxkyc/yjAAQcccMABBxxwVuN2uol3y2cunK+b2H9zgAPOZlwU6eriOAYOwxK453EWBjjauHWvmvak0S9r1E91Rysq1xe+nyU6HTdKV+dG4v76y8JfZ2VaMK3U3fUtL+/MNBxjqahKvZ7z/bmzBMfETrNn//KCF0twRarb9fUNL8ABtyTOxgAHHHAm4JItBds2GcXJkgKulKM43lLAtXwU50puv41LdxTHHNmWVs+7bdnKH6D7D10uk9DiJJK77F84agEOOOCAAw444CzNHwesR0NavrQNAAAAAElFTkSuQmCC" class="internal" width="220" height="220" />

### Parameters

`x`  
Distance to move in the horizontal direction. Positive values are to the right, and negative to the left.

`y`  
Distance to move in the vertical direction. Positive values are down, and negative are up.

## Examples

### Moving a shape

This example draws a square that is moved from its default position by the `translate()` method. An unmoved square of the same size is then drawn for comparison.

#### HTML

    <canvas id="canvas"></canvas>

#### JavaScript

The `translate()` method translates the context by 110 horizontally and 30 vertically. The first square is shifted by those amounts from its default position.

    const canvas = document.getElementById('canvas');
    const ctx = canvas.getContext('2d');

    // Moved square
    ctx.translate(110, 30);
    ctx.fillStyle = 'red';
    ctx.fillRect(0, 0, 80, 80);

    // Reset current transformation matrix to the identity matrix
    ctx.setTransform(1, 0, 0, 1, 0, 0);

    // Unmoved square
    ctx.fillStyle = 'gray';
    ctx.fillRect(0, 0, 80, 80);

#### Result

The <span style="color: red;">moved square is red</span>, and the <span style="color: gray;">unmoved square is gray</span>.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/scripting.html#dom-context-2d-translate">HTML Living Standard<br />
<span class="small">The definition of 'CanvasRenderingContext2D.translate' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`translate`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/translate" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/translate</a>
