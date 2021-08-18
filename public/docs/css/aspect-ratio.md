# aspect-ratio

The `aspect-ratio` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets a **preferred aspect ratio** for the box, which will be used in the calculation of auto sizes and some other layout functions.

    aspect-ratio: 1 / 1;

    /* Global values */
    aspect-ratio: inherit;
    aspect-ratio: initial;
    aspect-ratio: unset;

### Values

[`<auto>`](width)  
Replaced elements with an intrinsic aspect ratio use _that_ aspect ratio, otherwise the box has no preferred aspect ratio. Size calculations involving intrinsic aspect ratio always work with the content box dimensions.

[`<ratio>`](ratio)  
The box’s preferred aspect ratio is the specified ratio of `width` / `height`. Size calculations involving preferred aspect ratio work with the dimensions of the box specified by `box-sizing`.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>auto</code></td></tr><tr class="even"><td>Applies to</td><td>all elements except inline boxes and internal ruby or table boxes</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    auto | <ratio>

## Examples

### Examples of values for aspect-ratio

    aspect-ratio: 1 / 1;
    aspect-ratio: 16 / 9;

## Mapping width and height to aspect-ratio

Browsers have added an internal `aspect-ratio` property that applies to replaced elements and other related elements that accept `width` and `height` attributes. This appears in the browser's internal UA stylesheet.

In Firefox, the internal stylesheet rule looks like this:

    img, input[type="image"], video, embed, iframe, marquee, object, table {
      aspect-ratio: attr(width) / attr(height);
    }

You can read more about this feature in [Setting Height And Width On Images Is Important Again](https://www.smashingmagazine.com/2020/03/setting-height-width-images-important-again/).

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-sizing-4/#aspect-ratio">CSS Box Sizing Module Level 4<br />
<span class="small">The definition of 'aspect-ratio' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`aspect-ratio`

88

84

88

83

Firefox 83 implements aspect-ratio for flex items.

81

Firefox 81 implements aspect-ratio for blocks and replaced elements.

No

74

No

88

88

No

No

No

No

## See also

- [Mapping the width and height attributes of media container elements to their aspect-ratio](https://developer.mozilla.org/en-US/docs/Web/Media/images/aspect_ratio_mapping)
- [Designing an aspect ratio unit for CSS](https://www.smashingmagazine.com/2019/03/aspect-ratio-unit-css/)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/aspect-ratio" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/aspect-ratio</a>
