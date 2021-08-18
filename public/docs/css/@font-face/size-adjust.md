# size-adjust

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `size-adjust` CSS descriptor defines a multiplier for glyph outlines and metrics associated with this font. This makes it easier to harmonize the designs of various fonts when rendered at the same font size.

The `size-adjust` descriptor behaves in a similar fashion to the [`font-size-adjust`](../font-size-adjust) property. It calculates an adjustment per font by matching ex heights.

## Syntax

    size-adjust: 90%;

### Values

`<percentage>`  
A [`<percentage>`](../percentage) value with an initial value of 100%.

All metrics associated with this font are scaled by the given percentage. This includes glyph advances, baseline tables, and overrides provided by [`@font-face`](../@font-face) descriptors.

## Formal definition

<span style="color:red;">Value not found in DB!</span>

## Formal syntax

{{csssyntax}}

## Examples

### Overriding metrics of a fallback font

The `size-adjust` property can help when overriding the metrics of a fallback font to better match those of a primary web font.

    @font-face {
      font-family: web-font;
      src: url("https://example.com/font.woff");
    }

    @font-face {
      font-family: local-font;
      src: local(Local Font);
      size-adjust: 90%;
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-fonts-5/#size-adjust-desc">CSS Fonts Module Level 5<br />
<span class="small">The definition of 'size-adjust' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`size-adjust`

No

No

89

No

No

No

No

No

No

No

No

No

## See also

- [`font-display`](font-display)
- [`font-family`](font-family)
- [`font-weight`](font-weight)
- [`font-style`](font-style)
- [`font-stretch`](font-stretch)
- [`font-variant`](font-variant)
- [`font-feature-settings`](../font-feature-settings)
- [`font-variation-settings`](font-variation-settings)
- [`src`](src)
- [`unicode-range descriptor`](unicode-range)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/@font-face/size-adjust" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/@font-face/size-adjust</a>
