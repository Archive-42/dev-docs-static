# descent-override

The `descent-override` CSS descriptor defines the descent metric for the font. The descent metric is the height below the baseline that CSS uses to lay out line boxes in an inline formatting context.

## Syntax

    descent-override: normal;
    descent-override: 90%;

### Values

`normal`  
The default value. When used the metric value is obtained from the font file.

`<percentage>`  
A [`<percentage>`](../percentage) value.

## Formal definition

<span style="color:red;">Value not found in DB!</span>

## Formal syntax

{{csssyntax}}

## Examples

### Overriding metrics of a fallback font

The `descent-override` property can help when overriding the metrics of a fallback font to better match those of a primary web font.

    @font-face {
      font-family: web-font;
      src: url("https://example.com/font.woff");
    }

    @font-face {
      font-family: local-font;
      src: local(Local Font);
      descent-override: 125%;
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-fonts-4/#descdef-font-face-descent-override">CSS Fonts Module Level 4<br />
<span class="small">The definition of 'descent-override' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

## Browser compatibility

No compatibility data found for `css.at-rules.font-face.descent-override`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

## See also

- [`ascent-override`](ascent-override)
- [`font-display`](font-display)
- [`font-family`](font-family)
- [`font-weight`](font-weight)
- [`font-style`](font-style)
- [`font-stretch`](font-stretch)
- [`font-variant`](font-variant)
- [`font-feature-settings`](../font-feature-settings)
- [`font-variation-settings`](font-variation-settings)
- [`line-gap-override`](line-gap-override)
- [`src`](src)
- [`src`](size-adjust)
- [`unicode-range descriptor`](unicode-range)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/@font-face/descent-override" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/@font-face/descent-override</a>
