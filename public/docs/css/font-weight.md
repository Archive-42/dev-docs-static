# font-weight

The `font-weight` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets the weight (or boldness) of the font. The weights available depend on the [`font-family`](font-family) that is currently set.

## Syntax

    /* Keyword values */
    font-weight: normal;
    font-weight: bold;

    /* Keyword values relative to the parent */
    font-weight: lighter;
    font-weight: bolder;

    /* Numeric keyword values */
    font-weight: 100;
    font-weight: 200;
    font-weight: 300;
    font-weight: 400;// normal
    font-weight: 500;
    font-weight: 600;
    font-weight: 700;// bold
    font-weight: 800;
    font-weight: 900;

    /* Global values */
    font-weight: inherit;
    font-weight: initial;
    font-weight: unset;

The `font-weight` property is specified using any one of the values listed below.

### Values

`normal`  
Normal font weight. Same as `400`.

`bold`  
Bold font weight. Same as `700`.

`lighter`  
One relative font weight lighter than the parent element. Note that only four font weights are considered for relative weight calculation; see the [Meaning of relative weights](#meaning_of_relative_weights) section below.

`bolder`  
One relative font weight heavier than the parent element. Note that only four font weights are considered for relative weight calculation; see the [Meaning of relative weights](#meaning_of_relative_weights) section below.

`<number>`  
A [`<number>`](number) value between 1 and 1000, inclusive. Higher numbers represent weights that are bolder than (or as bold as) lower numbers. Certain commonly used values correspond to common weight names, as described in the [Common weight name mapping](#common_weight_name_mapping) section below.

In earlier versions of the `font-weight` specification, the property accepts only keyword values and the numeric values 100, 200, 300, 400, 500, 600, 700, 800, and 900; non-variable fonts can only really make use of these set values, although fine-grained values (e.g. 451) will be translated to one of these values for non-variable fonts using the [Fallback weights](#fallback_weights) system.

CSS Fonts Level 4 extends the syntax to accept any number between 1 and 1000 and introduces [Variable fonts](#variable_fonts), which can make use of this much finer-grained range of font weights.

### Fallback weights

If the exact weight given is unavailable, then the following rule is used to determine the weight actually rendered:

- If the target weight given is between `400` and `500` inclusive:
  - Look for available weights between the target and `500`, in ascending order.
  - If no match is found, look for available weights less than the target, in descending order.
  - If no match is found, look for available weights greater than `500`, in ascending order.
- If a weight less than `400` is given, look for available weights less than the target, in descending order. If no match is found, look for available weights greater than the target, in ascending order.
- If a weight greater than `500` is given, look for available weights greater than the target, in ascending order. If no match is found, look for available weights less than the target, in descending order.

### Meaning of relative weights

When `lighter` or `bolder` is specified, the below chart shows how the absolute font weight of the element is determined.

Note that when using relative weights, only four font weights are considered — thin (100), normal (400), bold (700), and heavy (900). If a font-family has more weights available, they are ignored for the purposes of relative weight calculation.

<table><thead><tr class="header"><th>Inherited value</th><th><code>bolder</code></th><th><code>lighter</code></th></tr></thead><tbody><tr class="odd"><td>100</td><td>400</td><td>100</td></tr><tr class="even"><td>200</td><td>400</td><td>100</td></tr><tr class="odd"><td>300</td><td>400</td><td>100</td></tr><tr class="even"><td>400</td><td>700</td><td>100</td></tr><tr class="odd"><td>500</td><td>700</td><td>100</td></tr><tr class="even"><td>600</td><td>900</td><td>400</td></tr><tr class="odd"><td>700</td><td>900</td><td>400</td></tr><tr class="even"><td>800</td><td>900</td><td>700</td></tr><tr class="odd"><td>900</td><td>900</td><td>700</td></tr></tbody></table>

### Common weight name mapping

The numerical values `100` to `900` roughly correspond to the following common weight names (see the [OpenType specification](https://docs.microsoft.com/en-us/typography/opentype/spec/os2#usweightclass)):

<table><thead><tr class="header"><th>Value</th><th>Common weight name</th></tr></thead><tbody><tr class="odd"><td>100</td><td>Thin (Hairline)</td></tr><tr class="even"><td>200</td><td>Extra Light (Ultra Light)</td></tr><tr class="odd"><td>300</td><td>Light</td></tr><tr class="even"><td>400</td><td>Normal (Regular)</td></tr><tr class="odd"><td>500</td><td>Medium</td></tr><tr class="even"><td>600</td><td>Semi Bold (Demi Bold)</td></tr><tr class="odd"><td>700</td><td>Bold</td></tr><tr class="even"><td>800</td><td>Extra Bold (Ultra Bold)</td></tr><tr class="odd"><td>900</td><td>Black (Heavy)</td></tr><tr class="even"><td>950</td><td><a href="https://docs.microsoft.com/en-us/dotnet/api/system.windows.fontweights?view=netframework-4.8#remarks">Extra Black (Ultra Black)</a></td></tr></tbody></table>

### Variable fonts

Most fonts have a particular weight which corresponds to one of the numbers in [Common weight name mapping](#common_weight_name_mapping). However some fonts, called variable fonts, can support a range of weights with a more or less fine granularity, and this can give the designer a much closer degree of control over the chosen weight.

For TrueType or OpenType variable fonts, the "wght" variation is used to implement varying widths.

For the example below to work, you'll need a browser that supports the CSS Fonts Level 4 syntax in which font-weight can be any number between 1 and 1000.

#### HTML

    <header>
        <input type="range" id="weight" name="weight" min="1" max="1000" />
        <label for="weight">Weight</label>
    </header>
    <div class="container">
        <p class="sample">...it would not be wonderful to meet a Megalosaurus, forty feet long or so, waddling like an elephantine lizard up Holborn Hill.</p>
    </div>

#### CSS

    /*
    Mutator Sans is created by LettError (https://github.com/LettError/mutatorSans)
    and is used here under the terms of its license:
    https://github.com/LettError/mutatorSans/blob/master/LICENSE
    */

    @font-face {
      src: url('https://mdn.mozillademos.org/files/16011/MutatorSans.ttf');
      font-family:'MutatorSans';
      font-style: normal;
    }

    label {
      font: 1rem monospace;
      white-space: nowrap;
    }

    .container {
      max-height: 150px;
      overflow-y: auto;
    }

    .sample {
      text-transform: uppercase;
      font: 1.5rem 'MutatorSans', sans-serif;
    }

#### JavaScript

    let weightLabel = document.querySelector('label[for="weight"]');
    let weightInput = document.querySelector('#weight');
    let sampleText = document.querySelector('.sample');

    function update() {
      weightLabel.textContent = `font-weight: ${weightInput.value};`;
      sampleText.style.fontWeight = weightInput.value;
    }

    weightInput.addEventListener('input', update);

    update();

## Accessibility concerns

People experiencing low vision conditions may have difficulty reading text set with a `font-weight` value of `100` (Thin/Hairline) or `200` (Extra Light), especially if the font has a [low contrast color ratio](color#accessibility_concerns).

- [MDN Understanding WCAG, Guideline 1.4 explanations](https://developer.mozilla.org/en-US/docs/Web/Accessibility/Understanding_WCAG/Perceivable#guideline_1.4_make_it_easier_for_users_to_see_and_hear_content_including_separating_foreground_from_background)
- [Understanding Success Criterion 1.4.8 | W3C Understanding WCAG 2.0](https://www.w3.org/TR/UNDERSTANDING-WCAG20/visual-audio-contrast-visual-presentation.html)

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>normal</code></td></tr><tr class="even"><td>Applies to</td><td>all elements. It also applies to <a href="::first-letter"><code>::first-letter</code></a> and <a href="::first-line"><code>::first-line</code></a>.</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>yes</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>the keyword or the numerical value as specified, with <code>bolder</code> and <code>lighter</code> transformed to the real value</td></tr><tr class="odd"><td>Animation type</td><td>a <a href="#Interpolation">font weight</a></td></tr></tbody></table>

## Formal syntax

    <font-weight-absolute> | bolder | lighterwhere
    <font-weight-absolute> = normal | bold | [1,1000]>

## Examples

### Setting font weights

#### HTML

    <p>
      Alice was beginning to get very tired of sitting by her sister on the
      bank, and of having nothing to do: once or twice she had peeped into the
      book her sister was reading, but it had no pictures or conversations in
      it, "and what is the use of a book," thought Alice "without pictures or
      conversations?"
    </p>

    <div>I'm heavy<br/>
      <span>I'm lighter</span>
    </div>

#### CSS

    /* Set paragraph text to be bold. */
    p {
      font-weight: bold;
    }

    /* Set div text to two steps heavier than
       normal but less than a standard bold. */
    div {
     font-weight: 600;
    }

    /* Set span text to be one step lighter
       than its parent. */
    span {
      font-weight: lighter;
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-fonts-4/#font-weight-prop">CSS Fonts Module Level 4<br />
<span class="small">The definition of 'font-weight' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Defines <code>font-weight</code> to accept any numbers between 1 and 1000.</td></tr><tr class="even"><td><a href="https://drafts.csswg.org/css-fonts-3/#font-weight-prop">CSS Fonts Module Level 3<br />
<span class="small">The definition of 'font-weight' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>No change.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/CSS2/fonts.html#propdef-font-weight">CSS Level 2 (Revision 1)<br />
<span class="small">The definition of 'font-weight' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>No change.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/CSS1/#font-weight">CSS Level 1<br />
<span class="small">The definition of 'font-weight' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`font-weight`

2

12

1

3

3.5

1

1

18

4

10.1

1

1.0

`number`

62

17

61

No

49

11

62

62

61

46

11

8.0

## See Also

- [`font-style`](font-style)
- [`font-family`](font-family)
- [Fundamental text and font styling](https://developer.mozilla.org/en-US/docs/Learn/CSS/Styling_text/Fundamentals)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/font-weight" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/font-weight</a>
