# word-spacing

The `word-spacing` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets the length of space between words and between tags.

## Syntax

    /* Keyword value */
    word-spacing: normal;

    /* <length> values */
    word-spacing: 3px;
    word-spacing: 0.3em;

    /* <percentage> values */
    word-spacing: 50%;
    word-spacing: 200%;

    /* Global values */
    word-spacing: inherit;
    word-spacing: initial;
    word-spacing: unset;

### Values

`normal`  
The normal inter-word spacing, as defined by the current font and/or the browser.

[`<length>`](length)  
Specifies extra spacing in addition to the intrinsic inter-word spacing defined by the font.

[`<percentage>`](percentage)  
Specifies extra spacing as a percentage of the affected character’s advance width.

## Examples

### HTML

    <div id="mozdiv1">Here are many words...</div>
    <div id="mozdiv2">...and many more!</div>

### CSS

    #mozdiv1 {
      word-spacing: 15px;
    }

    #mozdiv2 {
      word-spacing: 5em;
    }

## Accessibility concerns

A large positive or negative `word-spacing` value will make the sentences the styling is applied to unreadable. For text styled with a very large positive value, the words will be so far apart that it will no longer appear to be a sentence. For text styled with a large negative value, the words will overlap each other to the point where the beginning and end of each word is unrecognizable.

Legible `word-spacing` must be determined on a case-by-case basis, as different font families have different character widths. There is no one value that can ensure all font families automatically maintain their legibility.

- [MDN Understanding WCAG, Guideline 1.4 explanations](https://developer.mozilla.org/en-US/docs/Web/Accessibility/Understanding_WCAG/Perceivable#guideline_1.4_make_it_easier_for_users_to_see_and_hear_content_including_separating_foreground_from_background)
- [Understanding Success Criterion 1.4.8 | W3C Understanding WCAG 2.0](https://www.w3.org/TR/UNDERSTANDING-WCAG20/visual-audio-contrast-visual-presentation.html)

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>normal</code></td></tr><tr class="even"><td>Applies to</td><td>all elements. It also applies to <a href="::first-letter"><code>::first-letter</code></a> and <a href="::first-line"><code>::first-line</code></a>.</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>yes</td></tr><tr class="even"><td>Percentages</td><td>refer to the width of the affected glyph</td></tr><tr class="odd"><td><a href="computed_value">Computed value</a></td><td>an optimum, minimum, and maximum value, each consisting of either an absolute length, a percentage, or the keyword <code>normal</code></td></tr><tr class="even"><td>Animation type</td><td>a <a href="length#interpolation">length</a></td></tr></tbody></table>

## Formal syntax

    normal | <length-percentage>where
    <length-percentage> = <length> | <percentage>

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-text-3/#propdef-word-spacing">CSS Text Module Level 3<br />
<span class="small">The definition of 'word-spacing' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Replaces the previous values with a <code>&lt;spacing-limit&gt;</code> value that defines the same thing, plus the <code>&lt;percentage&gt;</code> value. Allows up to three values describing the optimum, minimum, and maximum value.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/CSS2/text.html#propdef-word-spacing">CSS Level 2 (Revision 1)<br />
<span class="small">The definition of 'word-spacing' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>No change.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/CSS1/#word-spacing">CSS Level 1<br />
<span class="small">The definition of 'word-spacing' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`word-spacing`

1

12

1

6

3.5

1

1

18

4

14

1

1.0

`percentages`

No

No

45

No

No

6.1

No

No

45

No

6.1

No

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

14

5.1

1.0

## See also

- [`letter-spacing`](letter-spacing)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/word-spacing" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/word-spacing</a>
