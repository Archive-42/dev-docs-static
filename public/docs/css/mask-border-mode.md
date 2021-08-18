# mask-border-mode

The `mask-border-mode` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property specifies the blending mode used in a [mask border](mask-border).

## Syntax

    /* Keyword values */
    mask-border-mode: luminance;
    mask-border-mode: alpha;

    /* Global values */
    mask-border-mode: inherit;
    mask-border-mode: initial;
    mask-border-mode: unset;

### Values

`luminance`  
The luminance values of the mask border image are used as the mask values.

`alpha`  
The alpha values of the mask border image are used as the mask values.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>alpha</code></td></tr><tr class="even"><td>Applies to</td><td>all elements; In SVG, it applies to container elements excluding the <a href="https://developer.mozilla.org/en-US/docs/Web/SVG/Element/defs"><code>defs</code></a> element and all graphics elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    luminance | alpha

## Examples

### Basic usage

This property doesn't yet seem to have support anywhere. When browsers support it, it will specify the type of blending mode used for the mask border — luminance or alpha:

    mask-border-mode: luminance;
    mask-border-mode: alpha;

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.fxtf.org/css-masking-1/#propdef-mask-border-mode">CSS Masking Module Level 1<br />
<span class="small">The definition of 'mask-border-mode' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

## Browser compatibility

No compatibility data found for `css.properties.mask-border-mode`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

## See also

- [`mask-border`](mask-border)
- [`mask-border-outset`](mask-border-outset)
- [`mask-border-repeat`](mask-border-repeat)
- [`mask-border-source`](mask-border-source)
- [`mask-border-width`](mask-border-width)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/mask-border-mode" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/mask-border-mode</a>
