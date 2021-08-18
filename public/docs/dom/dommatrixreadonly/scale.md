# DOMMatrixReadOnly.scale()

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `scale()` method of the [`DOMMatrixReadOnly`](../dommatrixreadonly) interface creates a new matrix being the result of the original matrix with a scale transform applied.

## Syntax

The `scale()` method is specified with either one or six values.

    DOMMatrix.scale(scaleX[, scaleY][, scaleZ][, originX][, originY][, originZ])

### <span class="highlight-span">Parameters</span>

scaleX  
A multiplier for the scale value on the x-axis.

scaleY <span class="inlineIndicator optional optionalInline">Optional</span>  
A multiplier for the scale value on the y-axis. If not supplied, this defaults to the value of `scaleX`.

scaleZ <span class="inlineIndicator optional optionalInline">Optional</span>  
A multiplier for the scale value on the z-axis. If this value is anything other than 1, the resulting matrix will be 3D.

originX <span class="inlineIndicator optional optionalInline">Optional</span>  
An x-coordinate for the origin of the transformation. If no origin is supplied, this defaults to 0.

originY <span class="inlineIndicator optional optionalInline">Optional</span>  
A y-coordinate for the origin of the transformation. If no origin is supplied, this defaults to 0.

originZ <span class="inlineIndicator optional optionalInline">Optional</span>  
A z-coordinate for the origin of the transformation. If no origin is supplied, this defaults to 0. If this value is anything other than 0, the resulting matrix will be 3D.

### <span class="highlight-span">Return value</span>

Returns a [`DOMMatrix`](../dommatrix) containing a new matrix being the result of the matrix x and y dimensions being scaled by the given factor, centered on the origin given. The original matrix is not modified.

If a scale is applied about the z-axis, the resulting matrix will be a 4x4 3D matrix.

**Note**: At time of writing, Firefox still supports an older version of the specification that accepts either one or three values.

    DOMMatrix.scale(scale[, originX][, originY])

We'll show an example of how you can deal with the cross-browser support implications of this in the Examples section, below.

## Examples

This SVG contains three squares, one red, one blue, and one green, each positioned at the document origin:

    <svg width="250" height="250" viewBox="0 0 25 25">
      <rect width="25" height="25" fill="red" />
      <rect id="transformed" width="25" height="25" fill="blue" />
      <rect id="transformedOrigin" width="25" height="25" fill="green" />
    </svg>

This JavaScript first creates an identity matrix, then uses the `scale()` method to create a new matrix with a single parameter.

We test if the browser supports a six parameter `scale()` method by creating a new matrix using three parameters and observing it's `is2D` property — if this is `false` then the third parameter has been accepted by the browser as a `scaleZ` parameter, making this a 3D matrix.

We then create a new matrix scaled about a given origin, using either three or six parameters depending on the browser support.

These new matrices are then applied to the blue and green squares as a `transform`, changing their dimensions and position. The red square is left in place.

    const matrix = new DOMMatrixReadOnly();
    const scaledMatrix = matrix.scale(0.5);

    let scaledMatrixWithOrigin = matrix.scale(0.5, 25, 25);

    // if the browser has interpreted these parameters as scaleX, scaleY, scaleZ, the resulting matrix is 3D
    const browserExpectsSixParamScale = !scaledMatrixWithOrigin.is2D;
    if (browserExpectsSixParamScale) {
      scaledMatrixWithOrigin = matrix.scale(0.5, 0.5, 1, 25, 25, 0);
    }

    document.querySelector('#transformed').setAttribute('transform', scaledMatrix.toString());
    document.querySelector('#transformedOrigin').setAttribute('transform', scaledMatrixWithOrigin.toString());

<table><thead><tr class="header"><th>Screenshot</th><th>Live sample</th></tr></thead><tbody><tr class="odd"><td><img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAPoAAAD6AgMAAAD1grKuAAAACVBMVEX/AgEHAP8AgAGh+nfWAAAAVUlEQVRo3u3LMREAIAwEsOpBBSbwx4xKHHz3XrKnTrYr833f933f933f933f933f933f933f9/0Rv7FedH3f933f933f933f933f933f933f931/wv8QVEOfxRKYEwAAAABJRU5ErkJggg==" class="internal" /></td><td></td></tr></tbody></table>

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.fxtf.org/geometry/#dom-dommatrixreadonly-scale">Geometry Interfaces Module Level 1<br />
<span class="small">The definition of 'DOMMatrixReadOnly.scale()' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`scale`

61

79

33

Firefox 69 introduced support for the modern six-parameter syntax for `scale()`. Previously, it only supported the older three-parameter syntax: `scale(scaleX[, originX][, originY]]])`.

No

48

11

61

61

33

Firefox for Android 79 introduced support for the modern six-parameter syntax for `scale()`. Previously, it only supported the older three-parameter syntax: `scale(scaleX[, originX][, originY]]])`.

45

11

8.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/DOMMatrixReadOnly/scale" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/DOMMatrixReadOnly/scale</a>
