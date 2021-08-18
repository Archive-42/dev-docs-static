# font-size-adjust

The `font-size-adjust` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets the size of lower-case letters relative to the current font size (which defines the size of upper-case letters).

    /* Use the specified font size */
    font-size-adjust: none;

    /* Use a font size that makes lowercase
       letters half the specified font size */
    font-size-adjust: 0.5;

    /* Global values */
    font-size-adjust: inherit;
    font-size-adjust: initial;
    font-size-adjust: unset;

The property is useful since the legibility of fonts, especially at small sizes, is determined more by the size of lowercase letters than by the size of capital letters. Legibility can become an issue when the first-choice [`font-family`](font-family) is unavailable and its replacement has a significantly different aspect ratio (the ratio of the size of lowercase letters to the size of the font).

To use this property in a way that is compatible with browsers that do not support `font-size-adjust`, it is specified as a number that the [`font-size`](font-size) property is multiplied by. This means the value specified for the property should generally be the aspect ratio of the first choice font. For example, a style sheet that specifies:

    font-size: 14px;
    font-size-adjust: 0.5;

... is really specifying that the lowercase letters of the font should be `7px` high (0.5 × 14px). This will still produce reasonable results in browsers that do not support `font-size-adjust`, where a `14px` font will be used.

## Syntax

### Values

`none`  
Choose the size of the font based only on the [`font-size`](font-size) property.

[`<number>`](number)  
Choose the size of the font so that its lowercase letters (as determined by the x-height of the font) are the specified number times the [`font-size`](font-size).

The number specified should generally be the aspect ratio (ratio of x-height to font size) of the first choice [`font-family`](font-family). This means that the first-choice font, when available, will appear the same size in browsers, whether or not they support `font-size-adjust`.

`0` yields text of zero height (hidden text).

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>none</code></td></tr><tr class="even"><td>Applies to</td><td>all elements. It also applies to <a href="::first-letter"><code>::first-letter</code></a> and <a href="::first-line"><code>::first-line</code></a>.</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>yes</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>a <a href="number#interpolation">number</a></td></tr></tbody></table>

## Formal syntax

    none | <number>

## Examples

### Adjusting lower-case letter sizes

#### HTML

    <p class="times">This text uses the Times font (10px), which is hard to read in small sizes.</p>
    <p class="verdana">This text uses the Verdana font (10px), which has relatively large lowercase letters.</p>
    <p class="adjtimes">This is the 10px Times, but now adjusted to the same aspect ratio as the Verdana.</p>

#### CSS

    .times {
      font-family: Times, serif;
      font-size: 10px;
    }

    .verdana {
      font-family: Verdana, sans-serif;
      font-size: 10px;
    }

    .adjtimes {
      font-family: Times, serif;
      font-size-adjust: 0.58;
      font-size: 10px;
    }

#### Results

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-fonts-3/#propdef-font-size-adjust">CSS Fonts Module Level 3<br />
<span class="small">The definition of 'font-size-adjust' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

The CSS property `font-size-adjust` was initially defined in CSS 2, but dropped in CSS 2.1. It has been newly defined in CSS 3.

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

`font-size-adjust`

43

79

40

3

Before Firefox 40, `font-size-adjust: 0` was incorrectly interpreted as `font-size-adjust: none` ([bug 1144885](https://bugzil.la/1144885)).

1

Before Firefox 3, `font-size-adjust` was supported on Windows only.

No

30

No

No

43

4

30

No

No

## See also

- [`font-size`](font-size)
- [`font-weight`](font-weight)
- [Fundamental text and font styling](https://developer.mozilla.org/en-US/docs/Learn/CSS/Styling_text/Fundamentals)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/font-size-adjust" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/font-size-adjust</a>
