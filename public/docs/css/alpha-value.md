# &lt;alpha-value&gt;

The `<alpha-value>` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [data type](css_types) represents a value that can be either a [`<number>`](number) or a [`<percentage>`](percentage), specifying the **[alpha channel](https://developer.mozilla.org/en-US/docs/Glossary/Alpha)** or **transparency** of a color.

## Syntax

The value of an `<alpha-value>` is given as either a `<number>` or a `<percentage>`.

If given as a number, the useful range is 0 (fully transparent) to 1.0 (fully opaque), with decimal values in between; that is, 0.5 indicates that half of the foreground color is used and half of the background color is used. Values outside the range of 0 to 1 are permitted, but are [clamped](<https://en.wikipedia.org/wiki/Clamping_(graphics)>) to like within the range 0 to 1.

If the alpha value is given as a percentage, 0% corresponds to fully transparent while 100% indicates fully opaque.

## Interpolation

When animated, values of the `<alpha-value>` CSS data type are interpolated as real, floating-point numbers. The speed of the interpolation is determined by the [timing function](easing-function) associated with the animation.

## Examples

### Setting text color opacity

Here an alpha value is used to set partially transparent text:

    /* <rgba()> */
    color: rgba(34, 12, 64, 0.6);
    color: rgba(34.0 12 64 / 60%);

### Setting shape image threshold

Here an alpha value is used to determine which parts of an image are considered part of a shape:

    /* shape-image-threshold */
    shape-image-threshold: 70%;
    shape-image-threshold: 0.7;

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-color/#type-def-alpha-value">CSS Color Module Level 4<br />
<span class="small">The definition of '&lt;alpha-value&gt;' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>No significant change.</td></tr><tr class="even"><td><a href="https://drafts.csswg.org/css-color-3/#alphavaluedt">CSS Color Module Level 3<br />
<span class="small">The definition of '&lt;alpha-value&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Introduces <code>&lt;alpha-value&gt;</code> along with <code>rgba()</code> and <code>hsla()</code> functional notations.</td></tr></tbody></table>

## See also

- [Fundamental text and font styling](https://developer.mozilla.org/en-US/docs/Learn/CSS/Styling_text/Fundamentals)
- [CSS data types](css_types)
- [CSS Color](css_color)
- `<color>`

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/alpha-value" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/alpha-value</a>
