# circle()

The `circle()` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) function is one of the [`<basic-shape>`](../basic-shape) [data types](../css_types).

## Syntax

    shape-outside: circle(50%);
    clip-path: circle(6rem at 12rem 8rem);

### Values

`<shape-radius>`  
This may be a [`<length>`](../length), or a [`<percentage>`](../percentage) or values `closest-side` and `farthest-side`.

`closest-side`  
Uses the length from the center of the shape to the closest side of the reference box. For circles, this is the closest side in any dimension.

`farthest-side`  
Uses the length from the center of the shape to the farthest side of the reference box. For circles, this is the closest side in any dimension.

`<position>`  
Moves the center of the circle. May be a [`<length>`](../length), or a [`<percentage>`](../percentage), or a values such as `left`.

## Examples

### Basic circle

In the example below, the [`shape-outside`](../shape-outside) property has a value of `circle(50%)`, which defines a circle on a floated element for the text to flow round.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-shapes/#funcdef-circle">CSS Shapes Module Level 1<br />
<span class="small">The definition of 'circle()' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`circle()`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/basic-shape/circle()" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/basic-shape/circle()</a>
