# mask-repeat

The `mask-repeat` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets how mask images are repeated. A mask image can be repeated along the horizontal axis, the vertical axis, both axes, or not repeated at all.

    /* One-value syntax */
    mask-repeat: repeat-x;
    mask-repeat: repeat-y;
    mask-repeat: repeat;
    mask-repeat: space;
    mask-repeat: round;
    mask-repeat: no-repeat;

    /* Two-value syntax: horizontal | vertical */
    mask-repeat: repeat space;
    mask-repeat: repeat repeat;
    mask-repeat: round space;
    mask-repeat: no-repeat round;

    /* Multiple values */
    mask-repeat: space round, no-repeat;
    mask-repeat: round repeat, space, repeat-x;

    /* Global values */
    mask-repeat: inherit;
    mask-repeat: initial;
    mask-repeat: unset;

By default, the repeated images are clipped to the size of the element, but they can be scaled to fit (using `round`) or evenly distributed from end to end (using `space`).

## Syntax

One or more `<repeat-style>` values, separated by commas.

### Values

`<repeat-style>`  
The one-value syntax is a shorthand for the full two-value syntax:

<table><tbody><tr class="odd"><td><strong>Single value</strong></td><td><strong>Two-value equivalent</strong></td></tr><tr class="even"><td><code>repeat-x</code></td><td><code>repeat no-repeat</code></td></tr><tr class="odd"><td><code>repeat-y</code></td><td><code>no-repeat repeat</code></td></tr><tr class="even"><td><code>repeat</code></td><td><code>repeat repeat</code></td></tr><tr class="odd"><td><code>space</code></td><td><code>space space</code></td></tr><tr class="even"><td><code>round</code></td><td><code>round round</code></td></tr><tr class="odd"><td><code>no-repeat</code></td><td><code>no-repeat no-repeat</code></td></tr></tbody></table>

In the two-value syntax, the first value represents the horizontal repetition behavior and the second value represents the vertical behavior. Here is an explanation of how each option works for either direction:

<table><tbody><tr class="odd"><td><code>repeat</code></td><td>The image is repeated as much as needed to cover the whole mask painting area. The last image will be clipped if it doesn't fit.</td></tr><tr class="even"><td><code>space</code></td><td>The image is repeated as much as possible without clipping. The first and last images are pinned to either side of the element, and whitespace is distributed evenly between the images. The <a href="mask-position"><code>mask-position</code></a> property is ignored unless only one image can be displayed without clipping. The only case where clipping happens using <code>space</code> is when there isn't enough room to display one image.</td></tr><tr class="odd"><td><code>round</code></td><td>As the allowed space increases in size, the repeated images will stretch (leaving no gaps) until there is room for another one to be added. When the next image is added, all of the current ones compress to allow room. Example: An image with an original width of 260px, repeated three times, might stretch until each repetition is 300px wide, and then another image will be added. They will then compress to 225px.</td></tr><tr class="even"><td><code>no-repeat</code></td><td>The image is not repeated (and hence the mask painting area will not necessarily be entirely covered). The position of the non-repeated mask image is defined by the <a href="mask-position"><code>mask-position</code></a> CSS property.</td></tr></tbody></table>

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>no-repeat</code></td></tr><tr class="even"><td>Applies to</td><td>all elements; In SVG, it applies to container elements excluding the <a href="https://developer.mozilla.org/en-US/docs/Web/SVG/Element/defs"><code>defs</code></a> element and all graphics elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>Consists of two keywords, one per dimension</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    <repeat-style>#where
    <repeat-style> = repeat-x | repeat-y | [ repeat | space | round | no-repeat ]{1,2}

## Examples

### Setting repeat for a single mask

### Multiple mask image support

You can specify a different `<repeat-style>` for each mask image, separated by commas:

    .examplethree {
      mask-image: url('mask1.png'), url('mask2.png');
      mask-repeat: repeat-x, repeat-y;
    }

Each image is matched with the corresponding repeat style, from first specified to last.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.fxtf.org/css-masking-1/#the-mask-repeat">CSS Masking Module Level 1<br />
<span class="small">The definition of 'mask-repeat' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`mask-repeat`

1

18

53

20-53

No

15

3.2

2

18

53

20-53

14

3.2

1.0

## See also

- [Clipping and Masking in CSS](https://css-tricks.com/clipping-masking-css/)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/mask-repeat" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/mask-repeat</a>
