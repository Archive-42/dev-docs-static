# CSSTransformComponent

The `CSSTransformComponent` interface of the of the [CSS_Object_Model\#css_typed_object_model](css_object_model#css_typed_object_model) is part of the [`CSSTransformValue`](csstransformvalue) interface.

## Properties

[`CSSTransformComponent.is2D`](csstransformcomponent/is2d) <span class="badge inline readonly">Read only </span>  
Returns a boolean indicting whether the transform is 2D or 3D.

## Methods

[`CSSTransformComponent.toMatrix()`](csstransformcomponent/tomatrix)  
Returns a new [`DOMMatrix`](dommatrix) object.

[`CSSTransformComponent.toString()`](csstransformcomponent/tostring)  
A [`DOMString`](domstring) in the form of a CSS [`transforms function`](https://developer.mozilla.org/en-US/docs/Web/CSS/transform-function).

This will use the value of `is2D` to return either a 2D or 3D transform. For example if the component represents [`CSSRotate`](cssrotate) and `is2D` is false then the string returned will be in the form of the CSS transformation `rotate3D()` function. If true the string returned will be in the form of the 2-dimensional `rotate3D()` function.

## Examples

To do

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.css-houdini.org/css-typed-om-1/#csstransformcomponent">CSS Typed OM Level 1<br />
<span class="small">The definition of 'CSSTransformComponent' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`CSSTransformComponent`

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

`is2D`

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

`toString`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CSSTransformComponent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CSSTransformComponent</a>
