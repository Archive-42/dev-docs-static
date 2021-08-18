# font-style

The `font-style` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets whether a font should be styled with a normal, italic, or oblique face from its [`font-family`](font-family).

**Italic** font faces are generally cursive in nature, usually using less horizontal space than their unstyled counterparts, while **oblique** faces are usually just sloped versions of the regular face. When the specified style is not available, both italic and oblique faces are simulated by artificially sloping the glyphs of the regular face (use [`font-synthesis`](font-synthesis) to control this behavior).

## Syntax

    font-style: normal;
    font-style: italic;
    font-style: oblique;
    font-style: oblique 10deg;

    /* Global values */
    font-style: inherit;
    font-style: initial;
    font-style: unset;

The `font-style` property is specified as a single keyword chosen from the list of values below, which can optionally include an angle if the keyword is `oblique`.

### Values

`normal`  
Selects a font that is classified as `normal` within a [`font-family`](font-family).

`italic`  
Selects a font that is classified as `italic`. If no italic version of the face is available, one classified as `oblique` is used instead. If neither is available, the style is artificially simulated.

`oblique`  
Selects a font that is classified as `oblique`. If no oblique version of the face is available, one classified as `italic` is used instead. If neither is available, the style is artificially simulated.

`oblique` `<angle>`  
Selects a font classified as `oblique`, and additionally specifies an angle for the slant of the text. If one or more oblique faces are available in the chosen font family, the one that most closely matches the specified angle is chosen. If no oblique faces are available, the browser will synthesize an oblique version of the font by slanting a normal face by the specified amount. Valid values are degree values of `-90deg` to `90deg` inclusive. If an angle is not specified, an angle of 14 degrees is used. Positive values are slanted to the end of the line, while negative values are slanted towards the beginning.

In general, for a requested angle of 14 degrees or greater, larger angles are preferred; otherwise, smaller angles are preferred (see the spec's [font matching section](https://drafts.csswg.org/css-fonts-4/#font-matching-algorithm) for the precise algorithm).

### Variable fonts

Variable fonts can offer a fine control over the degree to which an oblique face is slanted. You can select this using the `<angle>` modifier for the `oblique` keyword.

For TrueType or OpenType variable fonts, the `"slnt"` variation is used to implement varying slant angles for oblique, and the `"ital"` variation with a value of 1 is used to implement italic values. See [`font-variation-settings`](font-variation-settings).

For the example below to work, you'll need a browser that supports the CSS Fonts Level 4 syntax in which `font-style: oblique` can accept an `<angle>`.

#### HTML

    <header>
        <input type="range" id="slant" name="slant" min="-90" max="90" />
        <label for="slant">Slant</label>
    </header>
    <div class="container">
        <p class="sample">...it would not be wonderful to meet a Megalosaurus, forty feet long or so, waddling like an elephantine lizard up Holborn Hill.</p>
    </div>

#### CSS

    /*
    AmstelvarAlpha-VF is created by David Berlow (https://github.com/TypeNetwork/Amstelvar)
    and is used here under the terms of its license:
    https://github.com/TypeNetwork/Amstelvar/blob/master/OFL.txt
    */

    @font-face {
      src: url('https://mdn.mozillademos.org/files/16044/AmstelvarAlpha-VF.ttf');
      font-family:'AmstelvarAlpha';
      font-style: normal;
    }

    label {
      font: 1rem monospace;
    }

    .container {
      max-height: 150px;
      overflow: scroll;
    }

    .sample {
      font: 2rem 'AmstelvarAlpha', sans-serif;
    }

#### JavaScript

    let slantLabel = document.querySelector('label[for="slant"]');
    let slantInput = document.querySelector('#slant');
    let sampleText = document.querySelector('.sample');

    function update() {
      let slant = `oblique ${slantInput.value}deg`;
      slantLabel.textContent = `font-style: ${slant};`;
      sampleText.style.fontStyle = slant;
    }

    slantInput.addEventListener('input', update);

    update();

## Accessibility concerns

Large sections of text set with a `font-style` value of `italic` may be difficult for people with cognitive concerns such as Dyslexia to read.

- [MDN Understanding WCAG, Guideline 1.4 explanations](https://developer.mozilla.org/en-US/docs/Web/Accessibility/Understanding_WCAG/Perceivable#guideline_1.4_make_it_easier_for_users_to_see_and_hear_content_including_separating_foreground_from_background)
- [W3C Understanding WCAG 2.1](https://www.w3.org/TR/WCAG21/#visual-presentation)

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>normal</code></td></tr><tr class="even"><td>Applies to</td><td>all elements. It also applies to <a href="::first-letter"><code>::first-letter</code></a> and <a href="::first-line"><code>::first-line</code></a>.</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>yes</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    normal | italic | oblique <angle>?

## Examples

### Font styles

    .normal {
      font-style: normal;
    }

    .italic {
      font-style: italic;
    }

    .oblique {
      font-style: oblique;
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-fonts-4/#font-style-prop">CSS Fonts Module Level 4<br />
<span class="small">The definition of 'font-style' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Adds the ability to specify an angle after <code>oblique</code></td></tr><tr class="even"><td><a href="https://drafts.csswg.org/css-fonts-3/#font-style-prop">CSS Fonts Module Level 3<br />
<span class="small">The definition of 'font-style' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>No change</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/CSS2/fonts.html#propdef-font-style">CSS Level 2 (Revision 1)<br />
<span class="small">The definition of 'font-style' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>No change</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/CSS1/#font-style">CSS Level 1<br />
<span class="small">The definition of 'font-style' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`font-style`

1

12

1

Before Firefox 44, `oblique` was not distinguished from `italic`.

4

7

1

1

18

4

Before Firefox 44, `oblique` was not distinguished from `italic`.

10.1

1

1.0

`oblique-angle`

No

No

61

No

No

No

No

No

61

No

No

No

## See also

- [`font-style`](font-style)
- [`font-weight`](font-weight)
- [Fundamental text and font styling](https://developer.mozilla.org/en-US/docs/Learn/CSS/Styling_text/Fundamentals)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/font-style" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/font-style</a>
