# CSSTransformComponent.toMatrix()

The `toMatrix()` method of the [`CSSTransformComponent`](../csstransformcomponent) interface returns a [`DOMMatrix`](../dommatrix) object.

All transform functions can be represented mathematically as a 4x4 transformation matrix. This is explained in detail in [Understanding the CSS Transforms matrix](https://dev.opera.com/articles/understanding-the-css-transforms-matrix/).

The `is2D` property affects what transform, and therefore type of matrix that will be returned. CSS 2D and 3D transforms are different for legacy reasons. A brief explanation of 2D vs. 3D transforms can be found in [Using CSS transforms](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Transforms/Using_CSS_transforms).

## Syntax

    var matrix = CSSTransformComponent.toMatrix();

### Parameters

None

### Return value

A [`DOMMatrix`](../dommatrix) object

### Exceptions

[`TypeError`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypeError)  
Raised if any lengths involved in generating the matrix are not compatible units with px (such as relative lengths or percentages).

## Examples

To Do

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.css-houdini.org/css-typed-om-1/#dom-csstransformcomponent-tomatrix">CSS Typed OM Level 1<br />
<span class="small">The definition of 'toMatrix()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`toMatrix`

66

79

No

No

53

No

66

66

No

47

No

9.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CSSTransformComponent/toMatrix" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CSSTransformComponent/toMatrix</a>
