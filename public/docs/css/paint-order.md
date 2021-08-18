# paint-order

The `paint-order` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property lets you control the order in which the fill and stroke (and painting markers) of text content and shapes are drawn.

## Syntax

    /* Normal */
    paint-order: normal;

    /* Single values */
    paint-order: stroke; /* draw the stroke first, then fill and markers */
    paint-order: markers; /* draw the markers first, then fill and stroke */

    /* Multiple values */
    paint-order: stroke fill; /* draw the stroke first, then the fill, then the markers */
    paint-order: markers stroke fill; /* draw markers, then stroke, then fill */

If no value is specified, the default paint order is `fill`, `stroke`, `markers`.

When one value is specified, that one is painted first, followed by the other two in their default order relative to one another. When two values are specified, they will be painted in the order they are specified in, followed by the unspecified one.

**Note**: In the case of this property, markers are only appropriate when drawing SVG shapes involving the use of the `marker-*` properties (e.g. `marker-start`) and `<marker>` element. They do not apply to HTML text, so in that case, you can only determine the order of `stroke` and `fill`.

### Values

`normal`  
Paint the different items in normal paint order.

`stroke`,  
`fill`,  
`markers`  
Specify some or all of these values in the order you want them to be painted in.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>normal</code></td></tr><tr class="even"><td>Applies to</td><td>text elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>yes</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    normal | [ fill || stroke || markers ]

## Examples

### Reversing the paint order of stroke and fill

#### SVG

    <svg xmlns="http://www.w3.org/2000/svg" width="400" height="200">
      <text x="10" y="75">stroke in front</text>
      <text x="10" y="150" class="stroke-behind">stroke behind</text>
    </svg>

#### CSS

    text {
      font-family: sans-serif;
      font-size: 50px;
      font-weight: bold;
      fill: black;
      stroke: red;
      stroke-width: 4px;
    }

    .stroke-behind {
      paint-order: stroke fill;
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://svgwg.org/svg2-draft/painting.html#PaintOrder">Scalable Vector Graphics (SVG) 2<br />
<span class="small">The definition of 'paint-order' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`paint-order`

35

17

60

No

22

8

37

35

60

22

8

3.0

## See also

- [CSS Tricks: paint-order](https://css-tricks.com/almanac/properties/p/paint-order/)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/paint-order" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/paint-order</a>
