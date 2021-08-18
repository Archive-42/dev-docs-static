# DOMMatrixReadOnly.translate()

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `translate()` method of the [`DOMMatrixReadOnly`](../dommatrixreadonly) interface creates a new matrix being the result of the original matrix with a translation applied.

## Syntax

The `translate()` method accepts two or three values.

    DOMMatrix.translate(translateX, translateY[, translateZ])

### <span class="highlight-span">Parameters</span>

translateX  
A number representing the abscissa (x-coordinate) of the translating vector.

translateY  
A number representing the ordinate (y-coordinate) of the translating vector.

translateZ <span class="inlineIndicator optional optionalInline">Optional</span>  
A number representing the z component of the translating vector. If not supplied, this defaults to 0. If this is anything other than 0, the resulting matrix will be 3D.

### <span class="highlight-span">Return value</span>

Returns a [`DOMMatrix`](../dommatrix) containing a new matrix being the result of the matrix being translated by the given vector. The original matrix is not modified.

If a translation is applied about the z-axis, the resulting matrix will be a 4x4 3D matrix.

## Examples

This SVG contains two squares, one red and one blue, each positioned at the document origin:

    <svg width="250" height="250" viewBox="0 0 50 50">
      <rect width="25" height="25" fill="red" />
      <rect id="transformed" width="25" height="25" fill="blue" />
    </svg>

The following JavaScript first creates an identity matrix, then uses the `translate()` method to create a new, translated matrix — which is then applied to the blue square as a `transform`. The red square is left in place.

    const matrix = new DOMMatrixReadOnly().translate(25, 25);

    document.querySelector('#transformed').setAttribute('transform', matrix.toString());

<table><thead><tr class="header"><th>Screenshot</th><th>Live sample</th></tr></thead><tbody><tr class="odd"><td><img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAPsAAAD7BAMAAABeXP+VAAAAHlBMVEX/AgEHAP////+2tv+hof//SEj/XV1JR/9eXP/lfZfi0j/TAAAAq0lEQVR42u3OMQ2AUBAFwbNARXvBAR39RwEiUEKBAAQj4jWEzBqYrYo6lqguPB6Px+PxeDwej8fj8Xg8Ho/H4/F4PB6Px+PxeDwej8fj8Xg8Ho/H4/F4PB6Px+PxeDwej/8Uf0Y9e9LoyvbXKWnG4/F4PB6Px+PxeDwej8fj8Xg8Ho/H4/F4PB6Px+PxeDwej8fj8Xg8Ho/H4/F4PB6Px+Px+F/x2510pXxYv3X9vrSdLMIGAAAAAElFTkSuQmCC" class="internal" /></td><td></td></tr></tbody></table>

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.fxtf.org/geometry/#dom-dommatrixreadonly-translate">Geometry Interfaces Module Level 1<br />
<span class="small">The definition of 'DOMMatrixReadOnly.translate()' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

61

79

33

No

48

11

61

61

33

45

11

8.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/DOMMatrixReadOnly/translate" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/DOMMatrixReadOnly/translate</a>
