# ellipse()

The `ellipse()` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) function is one of the [`<basic-shape>`](../basic-shape) [data types](../css_types).

## Syntax

    shape-outside: ellipse(40% 50% at left);
    shape-outside: ellipse(closest-side farthest-side at 30%);

An ellipse is essentially a squashed circle and so `ellipse()` acts in a very similar way to [`circle()`](<circle()>) except that we have to specify two radii x and y.

### Values

`<shape-radius>`  
Two radii, x and y in that order. These may be a [`<length>`](../length), or a [`<percentage>`](../percentage) or values `closest-side` and `farthest-side`.

`closest-side`  
Uses the length from the center of the shape to the closest side of the reference box. For ellipses, this is the closest side in the radius dimension.

`farthest-side`  
Uses the length from the center of the shape to the farthest side of the reference box. For ellipses, this is the farthest side in the radius dimension.

`<position>`  
Moves the center of the ellipse. May be a [`<length>`](../length), or a [`<percentage>`](../percentage), or a values such as `left`.

## Examples

### Basic ellipse() example

This example shows an ellipse with an x radius of 40%, a y radius of 50% and the position being left. This means that the centre of the ellipse is on the left edge of the box giving us a half ellipse shape to wrap our text around. You can change these values to see how the ellipse changes.

### Using closest-side / farthest-side values

The keyword values of `closest-side` and `farthest-side` are useful to create a quick ellipse based on the size of the floated element reference box.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-shapes/#funcdef-ellipse">CSS Shapes Module Level 1<br />
<span class="small">The definition of 'ellipse()' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

## Browser compatibility

No compatibility data found for `css.types.basic-shape.ellipse`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

## See also

- Properties that use this data type: [`clip-path`](../clip-path), [`shape-outside`](../shape-outside)
- [Guide to Basic Shapes](../css_shapes/basic_shapes)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/basic-shape/ellipse()" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/basic-shape/ellipse()</a>
