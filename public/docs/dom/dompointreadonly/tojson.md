# DOMPointReadOnly.toJSON()

The [`DOMPointReadOnly`](../dompointreadonly) method `toJSON()` returns a [`DOMPointInit`](../dompointinit) object giving the [JSON](https://developer.mozilla.org/en-US/docs/Glossary/JSON) form of the point object.

## Syntax

    pointJSON = DOMPointReadOnly.toJSON();

### Parameters

None.

### Return value

A new [`DOMPointInit`](../dompointinit) object whose properties are set to the values in the `DOMPoint` or `DOMPointReadOnly` on which the method was called.

## Example

This example creates a [`DOMPoint`](../dompoint) object representing the top-left corner of the current window, in screen coordinates, then converts that to JSON.

    var topLeft = new DOMPoint(window.screenX, window.screenY);

    var pointJSON = topLeft.toJSON();

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.fxtf.org/geometry/#dom-dompointreadonly-tojson">Geometry Interfaces Module Level 1<br />
<span class="small">The definition of 'DOMPointReadOnly.toJSON()' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`toJSON`

61

79

62

No

48

10.1

61

61

62

45

10.3

8.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/DOMPointReadOnly/toJSON" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/DOMPointReadOnly/toJSON</a>
