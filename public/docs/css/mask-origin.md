# mask-origin

The `mask-origin` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets the origin of a mask.

    /* Keyword values */
    mask-origin: content-box;
    mask-origin: padding-box;
    mask-origin: border-box;
    mask-origin: margin-box;
    mask-origin: fill-box;
    mask-origin: stroke-box;
    mask-origin: view-box;

    /* Multiple values */
    mask-origin: padding-box, content-box;
    mask-origin: view-box, fill-box, border-box;

    /* Non-standard keyword values */
    -webkit-mask-origin: content;
    -webkit-mask-origin: padding;
    -webkit-mask-origin: border;

    /* Global values */
    mask-origin: inherit;
    mask-origin: initial;
    mask-origin: unset;

For elements rendered as a single box, this property specifies the mask positioning area. In other words, this property specifies the origin position of an image specified by the [`mask-image`](mask-image) CSS property. For elements rendered as multiple boxes, such as inline boxes on several lines or boxes on several pages, it specifies which boxes [`box-decoration-break`](box-decoration-break) operates upon to determine the mask positioning area.

## Syntax

One or more of the keyword values listed below, separated by commas.

### Values

`content-box`  
The position is relative to the content box.

`padding-box`  
The position is relative to the padding box. For single boxes `0 0` is the upper left corner of the padding edge, `100% 100%` is the lower right corner.

`border-box`  
The position is relative to the border box.

`margin-box`  
The position is relative to the margin box.

`fill-box`  
The position is relative to the object bounding box.

`stroke-box`  
The position is relative to the stroke bounding box.

`view-box`  
Uses the nearest SVG viewport as reference box. If a `viewBox` attribute is specified for the element creating the SVG viewport, the reference box is positioned at the origin of the coordinate system established by the `viewBox` attribute and the dimension of the reference box is set to the width and height values of the `viewBox` attribute.

`content` <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>  
Same as `content-box`.

`padding` <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>  
Same as `padding-box`.

`border` <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>  
Same as `border-box`.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>border-box</code></td></tr><tr class="even"><td>Applies to</td><td>all elements; In SVG, it applies to container elements excluding the <a href="https://developer.mozilla.org/en-US/docs/Web/SVG/Element/defs"><code>defs</code></a> element and all graphics elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    <geometry-box>#where
    <geometry-box> = <shape-box> | fill-box | stroke-box | view-boxwhere
    <shape-box> = <box> | margin-boxwhere
    <box> = border-box | padding-box | content-box

## Examples

### Setting mask origin to border-box

Try some of the other possible values by updating the CSS in the box below.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.fxtf.org/css-masking-1/#the-mask-origin">CSS Masking Module Level 1<br />
<span class="small">The definition of 'mask-origin' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`mask-origin`

1

The `margin-box` value is unsupported.

79

The `margin-box` value is unsupported.

53

20-53

No

15

The `margin-box` value is unsupported.

4

The `margin-box` value is unsupported.

2

The `margin-box` value is unsupported.

18

The `margin-box` value is unsupported.

53

20-53

14

The `margin-box` value is unsupported.

3.2

The `margin-box` value is unsupported.

1.0

The `margin-box` value is unsupported.

`fill-box`

No

No

No

No

No

No

See [bug 137293](https://webkit.org/b/137293).

No

No

No

No

No

No

`non_standard_values`

1

79

No

No

15

4

2

18

No

14

3.2

1.0

`stroke-box`

No

No

No

No

No

No

See [bug 137293](https://webkit.org/b/137293).

No

No

No

No

No

No

`view-box`

No

No

No

No

No

No

See [bug 137293](https://webkit.org/b/137293).

No

No

No

No

No

No

## See also

- [Clipping and Masking in CSS](https://css-tricks.com/clipping-masking-css/)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/mask-origin" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/mask-origin</a>
