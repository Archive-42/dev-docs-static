# mask-position

The `mask-position` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets the initial position, relative to the mask position layer set by [`mask-origin`](mask-origin), for each defined mask image.

    /* Keyword values */
    mask-position: top;
    mask-position: bottom;
    mask-position: left;
    mask-position: right;
    mask-position: center;

    /* <position> values */
    mask-position: 25% 75%;
    mask-position: 0px 0px;
    mask-position: 10% 8em;

    /* Multiple values */
    mask-position: top right;
    mask-position: 1rem 1rem, center;

    /* Global values */
    mask-position: inherit;
    mask-position: initial;
    mask-position: unset;

## Syntax

One or more `<position>` values, separated by commas.

### Values

[`<position>`](position_value)  
One to four values representing a 2D position regarding the edges of the element's box. Relative or absolute offsets can be given. Note that the position can be set outside of the element's box.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>center</code></td></tr><tr class="even"><td>Applies to</td><td>all elements; In SVG, it applies to container elements excluding the <a href="https://developer.mozilla.org/en-US/docs/Web/SVG/Element/defs"><code>defs</code></a> element and all graphics elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td>Percentages</td><td>refer to size of mask painting area minus size of mask layer image (see the text for <a href="background-position"><code>background-position</code></a>)</td></tr><tr class="odd"><td><a href="computed_value">Computed value</a></td><td>Consists of two keywords representing the origin and two offsets from that origin, each given as an absolute length (if given a &lt;length&gt;), otherwise as a percentage.</td></tr><tr class="even"><td>Animation type</td><td>repeatable list of simple list of length, percentage, or calc</td></tr></tbody></table>

## Formal syntax

    <position>#where
    <position> = [ [ left | center | right ] || [ top | center | bottom ] | [ left | center | right | <length-percentage> ] [ top | center | bottom | <length-percentage> ]? | [ [ left | right ] <length-percentage> ] && [ [ top | bottom ] <length-percentage> ] ]where
    <length-percentage> = <length> | <percentage>

## Examples

### Setting mask position

Change the `mask-position` value to any of the allowed values detailed above. If viewing the example in a Chromium-based browser change the value of `-webkit-mask-position`.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.fxtf.org/css-masking-1/#the-mask-position">CSS Masking Module Level 1<br />
<span class="small">The definition of 'mask-position' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`mask-position`

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

`three_value_syntax`

1-68

18-79

53-70

20-53

No

15-55

3.2

2-68

18-68

53

20-53

14-48

3.2

1.0-10.0

## See also

- [Clipping and Masking in CSS](https://css-tricks.com/clipping-masking-css/)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/mask-position" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/mask-position</a>
