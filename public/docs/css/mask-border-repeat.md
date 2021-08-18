# mask-border-repeat

The `mask-border-repeat` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets how the [edge regions](border-image-slice#edge-regions) of a source image are adjusted to fit the dimensions of an element's [mask border](mask-border).

## Syntax

    /* Keyword value */
    mask-border-repeat: stretch;
    mask-border-repeat: repeat;
    mask-border-repeat: round;
    mask-border-repeat: space;

    /* vertical | horizontal */
    mask-border-repeat: round stretch;

    /* Global values */
    mask-border-repeat: inherit;
    mask-border-repeat: initial;
    mask-border-repeat: unset;

The `mask-border-repeat` property may be specified using one or two values chosen from the list of values below.

- When **one** value is specified, it applies the same behavior on **all four sides**.
- When **two** values are specified, the first applies to the **top and bottom**, the second to the **left and right**.

### Values

`stretch`  
The source image's edge regions are stretched to fill the gap between each border.

`repeat`  
The source image's edge regions are tiled (repeated) to fill the gap between each border. Tiles may be clipped to achieve the proper fit.

`round`  
The source image's edge regions are tiled (repeated) to fill the gap between each border. Tiles may be stretched to achieve the proper fit.

`space`  
The source image's edge regions are tiled (repeated) to fill the gap between each border. Extra space will be distributed in between tiles to achieve the proper fit.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>stretch</code></td></tr><tr class="even"><td>Applies to</td><td>all elements; In SVG, it applies to container elements excluding the <a href="https://developer.mozilla.org/en-US/docs/Web/SVG/Element/defs"><code>defs</code></a> element and all graphics elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    [ stretch | repeat | round | space ]{1,2}

## Examples

### Basic usage

This property doesn't appear to be supported anywhere yet. When it eventually starts to be supported, it will serve to define how the border mask slice will repeat around the border — i.e. will it just repeat, or be scaled slightly so a whole number of slices fits, or be stretched so one slice fits?

    mask-border-repeat: round;

Chromium-based browsers support an outdated version of this property — `mask-box-image-repeat` — with a prefix:

    -webkit-mask-box-image-repeat: round;

**Note**: The `mask-border` page features a working example (using the out-of-date prefixed border mask properties supported in Chromium), so you can get an idea of the effect.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.fxtf.org/css-masking-1/#propdef-mask-border-repeat">CSS Masking Module Level 1<br />
<span class="small">The definition of 'mask-border-repeat' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`mask-border-repeat`

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
- [`mask-border-outset`](mask-border-outset)
- [`mask-border-source`](mask-border-source)
- [`mask-border-width`](mask-border-width)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/mask-border-repeat" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/mask-border-repeat</a>
