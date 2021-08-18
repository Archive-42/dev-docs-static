# mask-mode

The `mask-mode` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets whether the mask reference defined by [`mask-image`](mask-image) is treated as a luminance or alpha mask.

    /* Keyword values */
    mask-mode: alpha;
    mask-mode: luminance;
    mask-mode: match-source;

    /* Multiple values */
    mask-mode: alpha, match-source;

    /* Global values */
    mask-mode: inherit;
    mask-mode: initial;
    mask-mode: unset;

## Syntax

The `mask-mode` property is specified as one or more of the keyword values listed below, separated by commas.

### Values

`alpha`  
This keyword indicates that the transparency (alpha channel) values of the mask layer image should be used as the mask values.

`luminance`  
This keyword indicates that the luminance values of the mask layer image should be used as the mask values.

`match-source`  
If the [`mask-image`](mask-image) property is of type `<mask-source>`, the luminance values of the mask layer image should be used as the mask values.

If it is of type [`<image>`](image), the alpha values of the mask layer image should be used as the mask values.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>match-source</code></td></tr><tr class="even"><td>Applies to</td><td>all elements; In SVG, it applies to container elements excluding the <a href="https://developer.mozilla.org/en-US/docs/Web/SVG/Element/defs"><code>defs</code></a> element and all graphics elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    <masking-mode>#where
    <masking-mode> = alpha | luminance | match-source

## Examples

### Using alpha mask mode

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.fxtf.org/css-masking-1/#the-mask-mode">CSS Masking Module Level 1<br />
<span class="small">The definition of 'mask-mode' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`mask-mode`

No

No

53

No

No

No

No

No

53

No

No

No

## See also

- [Clipping and Masking in CSS](https://css-tricks.com/clipping-masking-css/)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/mask-mode" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/mask-mode</a>
