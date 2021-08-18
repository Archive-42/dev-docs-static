# mask-border-outset

The `mask-border-outset` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property specifies the distance by which an element's [mask border](mask-border) is set out from its border box.

## Syntax

    /* <length> value */
    mask-border-outset: 1rem;

    /* <number> value */
    mask-border-outset: 1.5;

    /* vertical | horizontal */
    mask-border-outset: 1 1.2;

    /* top | horizontal | bottom */
    mask-border-outset: 30px 2 45px;

    /* top | right | bottom | left */
    mask-border-outset: 7px 12px 14px 5px;

    /* Global values */
    mask-border-outset: inherit;
    mask-border-outset: initial;
    mask-border-outset: unset;

The `mask-border-outset` property may be specified as one, two, three, or four values. Each value is a [`<length>`](length) or [`<number>`](number). Negative values are invalid.

- When **one** value is specified, it applies the same outset to **all four sides**.
- When **two** values are specified, the first outset applies to the **top and bottom**, the second to the **left and right**.
- When **three** values are specified, the first outset applies to the **top**, the second to the **left and right**, the third to the **bottom**.
- When **four** values are specified, the outsets apply to the **top**, **right**, **bottom**, and **left** in that order (clockwise).

### Values

[`<length>`](length)  
The size of the mask border outset as a dimension.

[`<number>`](number)  
The size of the mask border outset as a multiple of the corresponding [`border-width`](border-width).

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>0</code></td></tr><tr class="even"><td>Applies to</td><td>all elements; In SVG, it applies to container elements excluding the <a href="https://developer.mozilla.org/en-US/docs/Web/SVG/Element/defs"><code>defs</code></a> element and all graphics elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified, but with relative lengths converted into absolute lengths</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    [ <length> | <number> ]{1,4}

## Examples

### Basic usage

This property doesn't appear to be supported anywhere yet. When it eventually starts to be supported, it will serve to move the mask away from the inner edge of the element's border box — you can use it to make the mask start from part way across the border, rather than the inside of it.

    mask-border-outset: 1rem;

Chromium-based browsers support an outdated version of this property — `mask-box-image-outset` — with a prefix:

    -webkit-mask-box-image-outset: 1rem;

**Note**: The `mask-border` page features a working example (using the out-of-date prefixed border mask properties supported in Chromium), so you can get an idea of the effect.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.fxtf.org/css-masking-1/#propdef-mask-border-outset">CSS Masking Module Level 1<br />
<span class="small">The definition of 'mask-border-outset' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`mask-border-outset`

1

79

No

See [bug 877294](https://bugzil.la/877294)

No

15

3.1

1

18

No

14

3

1.0

## See also

- [`mask-border`](mask-border)
- [`mask-border-mode`](mask-border-mode)
- [`mask-border-repeat`](mask-border-repeat)
- [`mask-border-source`](mask-border-source)
- [`mask-border-width`](mask-border-width)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/mask-border-outset" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/mask-border-outset</a>
