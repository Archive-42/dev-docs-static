# letter-spacing

The `letter-spacing` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets the horizontal spacing behavior between text characters. This value is added to the natural spacing between characters while rendering the text. Positive values of `letter-spacing` causes characters to spread farther apart, while negative values of `letter-spacing` bring characters closer together.

## Syntax

    /* Keyword value */
    letter-spacing: normal;

    /* <length> values */
    letter-spacing: 0.3em;
    letter-spacing: 3px;
    letter-spacing: .3px;

    /* Global values */
    letter-spacing: inherit;
    letter-spacing: initial;
    letter-spacing: unset;

### Values

`normal`  
The normal letter spacing for the current font. Unlike a value of `0`, this keyword allows the [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) to alter the space between characters in order to justify text.

[`<length>`](length)  
Specifies extra inter-character space _in addition to_ the default space between characters. Values may be negative, but there may be implementation-specific limits. User agents may not further increase or decrease the inter-character space in order to justify text.

## Accessibility concerns

A large positive or negative `letter-spacing` value will make the word(s) the styling is applied to unreadable. For text styled with a very large positive value, the letters will be so far apart that the word(s) will appear like a series of individual, unconnected letters. For text styled with a very large negative value, the letters will overlap each other to the point where the word(s) may be unrecognizable.

Legible letter-spacing must be determined on a case-by-case basis, as different font families have different character widths. There is no one value that can ensure all font families automatically maintain their legibility.

- [MDN Understanding WCAG, Guideline 1.4 explanations](https://developer.mozilla.org/en-US/docs/Web/Accessibility/Understanding_WCAG/Perceivable#guideline_1.4_make_it_easier_for_users_to_see_and_hear_content_including_separating_foreground_from_background)
- [Understanding Success Criterion 1.4.8 | W3C Understanding WCAG 2.0](https://www.w3.org/TR/UNDERSTANDING-WCAG20/visual-audio-contrast-visual-presentation.html)

## Internationalization concerns

Some written languages should not have any letter spacing applied. For instance, languages that use the Arabic script expect connected letters to remain visually connected, as in the following example. Appyling letter spacing will lead the text to look broken.

> شسيبتنمك

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>normal</code></td></tr><tr class="even"><td>Applies to</td><td>all elements. It also applies to <a href="::first-letter"><code>::first-letter</code></a> and <a href="::first-line"><code>::first-line</code></a>.</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>yes</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>an optimum value consisting of either an absolute length or the keyword <code>normal</code></td></tr><tr class="odd"><td>Animation type</td><td>a <a href="length#interpolation">length</a></td></tr></tbody></table>

## Formal syntax

    normal | <length>

## Examples

### Setting letter spacing

#### HTML

    <p class="normal">letter spacing</p>
    <p class="em-wide">letter spacing</p>
    <p class="em-wider">letter spacing</p>
    <p class="em-tight">letter spacing</p>
    <p class="px-wide">letter spacing</p>

#### CSS

    .normal   { letter-spacing: normal; }
    .em-wide  { letter-spacing: 0.4em; }
    .em-wider { letter-spacing: 1em; }
    .em-tight { letter-spacing: -0.05em; }
    .px-wide  { letter-spacing: 6px; }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-text-3/#letter-spacing-property">CSS Text Module Level 3<br />
<span class="small">The definition of 'letter-spacing' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>No change.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/CSS2/text.html#propdef-letter-spacing">CSS Level 2 (Revision 1)<br />
<span class="small">The definition of 'letter-spacing' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>No change.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/SVG11/text.html#LetterSpacingProperty">Scalable Vector Graphics (SVG) 1.1 (Second Edition)<br />
<span class="small">The definition of 'letter-spacing' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial SVG definition.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/CSS1/#letter-spacing">CSS Level 1<br />
<span class="small">The definition of 'letter-spacing' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`letter-spacing`

1

12

1

4

3.5

1

≤37

18

4

10.1

1

1.0

`svg`

1

12

72

9

7

5.1

≤37

18

No

10.1

5.1

1.0

## See also

- [`font-kerning`](font-kerning)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/letter-spacing" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/letter-spacing</a>
