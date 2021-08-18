# mask-border

The `mask-border` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [shorthand property](shorthand_properties) lets you create a mask along the edge of an element's border.

## Constituent properties

This property is a shorthand for the following CSS properties:

- [`mask-border-mode`](mask-border-mode)
- [`mask-border-outset`](mask-border-outset)
- [`mask-border-repeat`](mask-border-repeat)
- [`mask-border-slice`](mask-border-slice)
- [`mask-border-source`](mask-border-source)
- [`mask-border-width`](mask-border-width)

## Syntax

    /* source | slice */
    mask-border: url('border-mask.png') 25;

    /* source | slice | repeat */
    mask-border: url('border-mask.png') 25 space;

    /* source | slice | width */
    mask-border: url('border-mask.png') 25 / 35px;

    /* source | slice | width | outset | repeat | mode */
    mask-border: url('border-mask.png') 25 / 35px / 12px space alpha;

### Values

`<'mask-border-source'>`  
The source image. See [`mask-border-source`](mask-border-source).

`<'mask-border-slice'>`  
The dimensions for slicing the source image into regions. Up to four values may be specified. See [`mask-border-slice`](mask-border-slice).

`<'mask-border-width'>`  
The width of the border mask. Up to four values may be specified. See [`mask-border-width`](mask-border-width).

`<'mask-border-outset'>`  
The distance of the border mask from the element's outside edge. Up to four values may be specified. See [`mask-border-outset`](mask-border-outset).

`<'mask-border-repeat'>`  
Defines how the edge regions of the source image are adjusted to fit the dimensions of the border mask. Up to two values may be specified. See [`mask-border-repeat`](mask-border-repeat).

`<'mask-border-mode'>`  
Defines whether the source image is treated as a luminance mask or alpha mask. See [`mask-border-mode`](mask-border-mode).

## Formal definition

<table><colgroup><col style="width: 50%" /><col style="width: 50%" /></colgroup><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td>as each of the properties of the shorthand:<br />
<ul><li><a href="mask-border-mode"><code>mask-border-mode</code></a>: <code>alpha</code></li><li><a href="mask-border-outset"><code>mask-border-outset</code></a>: <code>0</code></li><li><a href="mask-border-repeat"><code>mask-border-repeat</code></a>: <code>stretch</code></li><li><a href="mask-border-slice"><code>mask-border-slice</code></a>: <code>0</code></li><li><a href="mask-border-source"><code>mask-border-source</code></a>: <code>none</code></li><li><a href="mask-border-width"><code>mask-border-width</code></a>: <code>auto</code></li></ul></td></tr><tr class="even"><td>Applies to</td><td>all elements; In SVG, it applies to container elements excluding the <a href="https://developer.mozilla.org/en-US/docs/Web/SVG/Element/defs"><code>defs</code></a> element and all graphics elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td>Percentages</td><td>as each of the properties of the shorthand:<br />
<ul><li><a href="mask-border-slice"><code>mask-border-slice</code></a>: refer to size of the mask border image</li><li><a href="mask-border-width"><code>mask-border-width</code></a>: relative to width/height of the mask border image area</li></ul></td></tr><tr class="odd"><td><a href="computed_value">Computed value</a></td><td>as each of the properties of the shorthand:<br />
<ul><li><a href="mask-border-mode"><code>mask-border-mode</code></a>: as specified</li><li><a href="mask-border-outset"><code>mask-border-outset</code></a>: as specified, but with relative lengths converted into absolute lengths</li><li><a href="mask-border-repeat"><code>mask-border-repeat</code></a>: as specified</li><li><a href="mask-border-slice"><code>mask-border-slice</code></a>: as specified</li><li><a href="mask-border-source"><code>mask-border-source</code></a>: as specified, but with <a href="url()"><code>url()</code></a> values made absolute</li><li><a href="mask-border-width"><code>mask-border-width</code></a>: as specified, but with relative lengths converted into absolute lengths</li></ul></td></tr><tr class="even"><td>Animation type</td><td>as each of the properties of the shorthand:<br />
<ul><li><a href="mask-border-mode"><code>mask-border-mode</code></a>: discrete</li><li><a href="mask-border-outset"><code>mask-border-outset</code></a>: discrete</li><li><a href="mask-border-repeat"><code>mask-border-repeat</code></a>: discrete</li><li><a href="mask-border-slice"><code>mask-border-slice</code></a>: discrete</li><li><a href="mask-border-source"><code>mask-border-source</code></a>: discrete</li><li><a href="mask-border-width"><code>mask-border-width</code></a>: discrete</li></ul></td></tr><tr class="odd"><td>Creates <a href="css_positioning/understanding_z_index/the_stacking_context">stacking context</a></td><td>yes</td></tr></tbody></table>

## Formal syntax

    <'mask-border-source'> || <'mask-border-slice'> [ / <'mask-border-width'>? [ / <'mask-border-outset'> ]? ]? || <'mask-border-repeat'> || <'mask-border-mode'>

## Examples

### Setting a bitmap-based mask border

In this example, we will mask an element's border with a diamond pattern. The source for the mask is a ".png" file of 90 by 90 pixels, with three diamonds going vertically and horizontally:

<img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAFoAAABaCAMAAAAPdrEwAAAACVBMVEX////u7u7u7u7XaHCtAAAAAnRSTlMAoKBFbtAAAADFSURBVHja7dgxCoMAEEXBbO5/6JQPa3easHYy8BAR/fh5HjOP0039fodpvq050Bxovqg50BxoDjQHmgPNVzUHmq9r/kZL7x1dNiuTdo8IKdcG5dqgXBuUa4Ny7cVybVCuDcq1Qbk2KNcG5dqgLNMjbzVqj3ysUXvkKwS1R76uUXvkpxG0QRnMEDCezOS7pXpL9ZbqLdVbqrdUb6neUr2lekv175bqvFH5kznf1hxoDjRf1BxoDjQHmgPNgearmgPN1zVf1B9dHy21wJOU0wAAAABJRU5ErkJggg==" width="90" height="90" />

To match the size of a single diamond, we will use a value of 90 divided by 3, or `30`, for slicing the image into corner and edge regions. A repeat value of `round` will make the mask slices fit evenly, i.e., without clipping or gaps.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.fxtf.org/css-masking-1/#propdef-mask-border">CSS Masking Module Level 1<br />
<span class="small">The definition of 'mask-border' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`mask-border`

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

- [`mask-border-mode`](mask-border-mode)
- [`mask-border-outset`](mask-border-outset)
- [`mask-border-repeat`](mask-border-repeat)
- [`mask-border-source`](mask-border-source)
- [`mask-border-width`](mask-border-width)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/mask-border" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/mask-border</a>
