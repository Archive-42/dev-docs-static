# mask-clip

The `mask-clip` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property determines the area which is affected by a mask. The painted content of an element must be restricted to this area.

    /* <geometry-box> values */
    mask-clip: content-box;
    mask-clip: padding-box;
    mask-clip: border-box;
    mask-clip: margin-box;
    mask-clip: fill-box;
    mask-clip: stroke-box;
    mask-clip: view-box;

    /* Keyword values */
    mask-clip: no-clip;

    /* Non-standard keyword values */
    -webkit-mask-clip: border;
    -webkit-mask-clip: padding;
    -webkit-mask-clip: content;
    -webkit-mask-clip: text;

    /* Multiple values */
    mask-clip: padding-box, no-clip;
    mask-clip: view-box, fill-box, border-box;

    /* Global values */
    mask-clip: inherit;
    mask-clip: initial;
    mask-clip: unset;

## Syntax

One or more of the keyword values listed below, separated by commas.

### Values

`content-box`  
The painted content is clipped to the content box.

`padding-box`  
The painted content is clipped to the padding box.

`border-box`  
The painted content is clipped to the border box.

`margin-box`  
The painted content is clipped to the margin box.

`fill-box`  
The painted content is clipped to the object bounding box.

`stroke-box`  
The painted content is clipped to the stroke bounding box.

`view-box`  
Uses the nearest SVG viewport as reference box. If a `viewBox` attribute is specified for the element creating the SVG viewport, the reference box is positioned at the origin of the coordinate system established by the `viewBox` attribute and the dimension of the reference box is set to the width and height values of the `viewBox` attribute.

`no-clip`  
The painted content is not clipped.

`border`<span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>  
This keyword behaves the same as `border-box`.

`padding`<span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>  
This keyword behaves the same as `padding-box`.

`content`<span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>  
This keyword behaves the same as `content-box`.

`text`<span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>  
This keyword clips the mask image to the text of the element.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>border-box</code></td></tr><tr class="even"><td>Applies to</td><td>all elements; In SVG, it applies to container elements excluding the <a href="https://developer.mozilla.org/en-US/docs/Web/SVG/Element/defs"><code>defs</code></a> element and all graphics elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    [ <geometry-box> | no-clip ]#where
    <geometry-box> = <shape-box> | fill-box | stroke-box | view-boxwhere
    <shape-box> = <box> | margin-boxwhere
    <box> = border-box | padding-box | content-box

## Examples

### Clipping a mask to the border box

Change the `mask-clip` value to any of the allowed values detailed above. If viewing the example in a Chromium-based browser change the value of `-webkit-mask-clip`.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.fxtf.org/css-masking-1/#the-mask-clip">CSS Masking Module Level 1<br />
<span class="small">The definition of 'mask-clip' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`mask-clip`

1

79

53

20-53

No

15

4

2

18

53

20-53

14

3.2

1.0

`border`

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

`content`

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

`padding`

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

`text`

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

## See also

- [Clipping and Masking in CSS](https://css-tricks.com/clipping-masking-css/)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/mask-clip" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/mask-clip</a>
