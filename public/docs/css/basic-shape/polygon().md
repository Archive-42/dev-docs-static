# polygon()

The `polygon()` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) function is one of the [`<basic-shape>`](../basic-shape) [data types](../css_types).

## Syntax

    clip-path: polygon(50% 2.4%, 34.5% 33.8%, 0% 38.8%, 25% 63.1%, 19.1% 97.6%);

### Values

`<fill-rule>`  
An optional value of `nonzero` (the default when omitted) or `evenodd`, which specifies the [filling rule](https://developer.mozilla.org/en-US/docs/Web/SVG/Attribute/fill-rule).

`[<length-percentage><length-percentage>]#`  
Three or more pairs of values (a polygon must at least draw a triangle). These values are co-ordinates drawn with reference to the reference box.

## Examples

### Basic polygon() example

In this example a shape is created for text to follow using the `polygon()`, you can change any of the values to see how the shape is changed.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-shapes/#funcdef-polygon">CSS Shapes Module Level 1<br />
<span class="small">The definition of 'polygon()' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`polygon()`

37

79

54

No

24

10.1

37

37

54

24

10.3

3.0

## See also

- Properties that use this data type: [`clip-path`](../clip-path), [`shape-outside`](../shape-outside)
- [Guide to Basic Shapes](../css_shapes/basic_shapes)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/basic-shape/polygon()" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/basic-shape/polygon()</a>
