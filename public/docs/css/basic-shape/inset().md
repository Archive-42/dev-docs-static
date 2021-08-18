# inset()

The `inset()` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) function is one of the [`<basic-shape>`](../basic-shape) [data types](../css_types). It defines an inset rectangle.

## Syntax

    shape-outside: inset(20px 50px 10px 0 round 50px);

### Values

`<length-percentage>{1.4}`  
When all of the four arguments are supplied they represent the top, right, bottom and left offsets from the reference box inward that define the positions of the edges of the inset rectangle. These arguments follow the syntax of the margin shorthand, that let you set all four insets with one, two or four values.

`<border-radius>`  
The optional [`<border-radius>`](../border-radius) argument(s) define rounded corners for the inset rectangle using the border-radius shorthand syntax.

When all of the first four arguments are supplied they represent the top, right, bottom and left offsets from the reference box inward that define the positions of the edges of the inset rectangle. These arguments follow the syntax of the margin shorthand, that let you set all four insets with one, two or four values.

## Examples

### Basic inset example

In the example below we have an `inset()` shape used to pull content over the floated element. Change the offset values to see how the shape changes.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-shapes/#funcdef-inset">CSS Shapes Module Level 1<br />
<span class="small">The definition of 'inset()' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`inset()`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/basic-shape/inset()" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/basic-shape/inset()</a>
