# shape-margin

The `shape-margin` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets a margin for a CSS shape created using [`shape-outside`](shape-outside).

The margin lets you adjust the distance between the edges of the shape (the **float element**) and the surrounding content.

## Syntax

    /* <length> values */
    shape-margin: 10px;
    shape-margin: 20mm;

    /* <percentage> value */
    shape-margin: 60%;

    /* Global values */
    shape-margin: inherit;
    shape-margin: initial;
    shape-margin: unset;

### Values

`<length-percentage>`  
Sets the margin of the shape to a [`<length>`](length) value or to a [`<percentage>`](percentage) of the width of the element's containing block.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>0</code></td></tr><tr class="even"><td>Applies to</td><td>floats</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td>Percentages</td><td>refer to the width of the containing block</td></tr><tr class="odd"><td><a href="computed_value">Computed value</a></td><td>as specified, but with relative lengths converted into absolute lengths</td></tr><tr class="even"><td>Animation type</td><td>a <a href="length#interpolation">length</a>, <a href="percentage#interpolation">percentage</a> or calc();</td></tr></tbody></table>

## Formal syntax

    <length-percentage>where
    <length-percentage> = <length> | <percentage>

## Examples

### Adding a margin to a polygon

#### HTML

    <section>
    <div class="shape"></div>
    We are not quite sure of any one thing in biology; our knowledge of geology
    is relatively very slight, and the economic laws of society are
    uncertain to every one except some individual who attempts to set them
    forth; but before the world was fashioned the square on the hypotenuse
    was equal to the sum of the squares on the other two sides of a right
    triangle, and it will be so after this world is dead; and the inhabitant
    of Mars, if one exists, probably knows its truth as we know it.</section>

#### CSS

    section {
      max-width: 400px;
    }

    .shape {
      float: left;
      width: 150px;
      height: 150px;
      background-color: maroon;
      clip-path: polygon(0 0, 150px 150px, 0 150px);
      shape-outside: polygon(0 0, 150px 150px, 0 150px);
      shape-margin: 20px;
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-shapes/#shape-margin-property">CSS Shapes Module Level 1<br />
<span class="small">The definition of 'shape-margin' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`shape-margin`

37

79

62

61-62

No

24

10.1

10.1

37

37

62

61-62

24

10.3

3.0

## See also

- [CSS Shapes](css_shapes)
- [Overview of CSS Shapes](css_shapes/overview_of_css_shapes)
- [`shape-outside`](shape-outside)
- [`shape-image-threshold`](shape-image-threshold)
- [`<basic-shape>`](basic-shape)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/shape-margin" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/shape-margin</a>
