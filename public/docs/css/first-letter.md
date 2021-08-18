# ::first-letter (:first-letter)

The `::first-letter` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [pseudo-element](pseudo-elements) applies styles to the first letter of the first line of a [block-level element](visual_formatting_model#block-level_elements_and_block_boxes), but only when not preceded by other content (such as images or inline tables).

    /* Selects the first letter of a <p> */
    p::first-letter {
      font-size: 130%;
    }

The first letter of an element is not always trivial to identify:

- Punctuation that precedes or immediately follows the first letter is included in the match. Punctuation includes any Unicode character defined in the _open_ (Ps), _close_ (Pe), _initial quote_ (Pi), _final quote_ (Pf), and _other punctuation_ (Po) classes.
- Some languages have digraphs that are always capitalized together, like the `IJ` in Dutch. In these cases, both letters of the digraph should be matched by the `::first-letter` pseudo-element.
- A combination of the [`::before`](::before) pseudo-element and the [`content`](content) property may inject some text at the beginning of the element. In that case, `::first-letter` will match the first letter of this generated content.

**Note**

CSS3 introduced the `::first-letter` notation (with two colons) to distinguish [pseudo-classes](pseudo-classes) from [pseudo-elements](pseudo-elements). Browsers also accept `:first-letter`, introduced in CSS2.

Browser support for digraphs such as `IJ` in Dutch is poor. Check the compatibility table below to see the current state of support.

## Allowable properties

Only a small subset of CSS properties can be used with the `::first-letter` pseudo-element:

- All font properties : [`font`](font), [`font-style`](font-style), [`font-feature-settings`](font-feature-settings), [`font-kerning`](font-kerning), [`font-language-override`](font-language-override), [`font-stretch`](font-stretch), [`font-synthesis`](font-synthesis), [`font-variant`](font-variant), [`font-variant-alternates`](font-variant-alternates), [`font-variant-caps`](font-variant-caps), [`font-variant-east-asian`](font-variant-east-asian), [`font-variant-ligatures`](font-variant-ligatures), [`font-variant-numeric`](font-variant-numeric), [`font-variant-position`](font-variant-position), [`font-weight`](font-weight), [`font-size`](font-size), [`font-size-adjust`](font-size-adjust), [`line-height`](line-height) and [`font-family`](font-family)
- All background properties : [`background`](background), [`background-color`](background-color), [`background-image`](background-image), [`background-clip`](background-clip), [`background-origin`](background-origin), [`background-position`](background-position), [`background-repeat`](background-repeat), [`background-size`](background-size), [`background-attachment`](background-attachment), and [`background-blend-mode`](background-blend-mode)
- All margin properties: [`margin`](margin), [`margin-top`](margin-top), [`margin-right`](margin-right), [`margin-bottom`](margin-bottom), [`margin-left`](margin-left)
- All padding properties: [`padding`](padding), [`padding-top`](padding-top), [`padding-right`](padding-right), [`padding-bottom`](padding-bottom), [`padding-left`](padding-left)
- All border properties: the shorthands [`border`](border), [`border-style`](border-style), [`border-color`](border-color), [`border-width`](border-width), [`border-radius`](border-radius), [`border-image`](border-image), and the longhands properties
- The [`color`](color) property
- The [`text-decoration`](text-decoration), [`text-shadow`](text-shadow), [`text-transform`](text-transform), [`letter-spacing`](letter-spacing), [`word-spacing`](word-spacing) (when appropriate), [`line-height`](line-height), [`text-decoration-color`](text-decoration-color), [`text-decoration-line`](text-decoration-line), [`text-decoration-style`](text-decoration-style), [`box-shadow`](box-shadow), [`float`](float), [`vertical-align`](vertical-align) (only if `float` is `none`) CSS properties

## Syntax

    /* CSS3 syntax */
    ::first-letter

    /* CSS2 syntax */
    :first-letter

## Examples

### Simple drop cap

In this example we will use the `::first-letter` pseudo-element to create a simple drop cap effect on the first letter of the paragraph coming right after the `<h2>`.

#### HTML

    <h2>My heading</h2>
    <p>Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor invidunt
      ut labore et dolore magna aliquyam erat, sed diam voluptua. At vero eos et accusam et justo duo
      dolores et ea rebum. Stet clita kasd gubergren, no sea takimata sanctus est.</p>
    <p>Duis autem vel eum iriure dolor in hendrerit in vulputate velit esse molestie consequat.</p>

#### CSS

    p {
      width: 500px;
      line-height: 1.5;
    }

    h2 + p::first-letter {
      color: white;
      background-color: black;
      border-radius: 2px;
      box-shadow: 3px 3px 0 red;
      font-size: 250%;
      padding: 6px 3px;
      margin-right: 6px;
      float: left;
    }

#### Result

### Effect on special punctuation and non-Latin characters

This example illustrates the effect of `::first-letter` on special punctuation and non-Latin characters.

#### HTML

    <p>Duis autem vel eum iriure dolor in hendrerit in vulputate velit esse molestie consequat.</p>
    <p>-The beginning of a special punctuation mark.</p>
    <p>_The beginning of a special punctuation mark.</p>
    <p>"The beginning of a special punctuation mark.</p>
    <p>'The beginning of a special punctuation mark.</p>
    <p>*The beginning of a special punctuation mark.</p>
    <p>#The beginning of a special punctuation mark.</p>
    <p>「特殊的汉字标点符号开头。</p>
    <p>《特殊的汉字标点符号开头。</p>
    <p>“特殊的汉字标点符号开头。</p>

#### CSS

    p::first-letter {
      color: red;
      font-size: 150%;
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-pseudo-4/#first-letter-pseudo">CSS Pseudo-Elements Level 4<br />
<span class="small">The definition of '::first-letter' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Generalizes allowed properties to typesetting, text decoration, inline layout properties, <a href="opacity"><code>opacity</code></a>, and <a href="box-shadow"><code>box-shadow</code></a>.</td></tr><tr class="even"><td><a href="https://drafts.csswg.org/css-text-decor-3/#text-shadow-property">CSS Text Decoration Module Level 3<br />
<span class="small">The definition of 'text-shadow with ::first-letter' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Allows the use of <a href="text-shadow"><code>text-shadow</code></a> with <code>::first-letter</code>.</td></tr><tr class="odd"><td><a href="https://drafts.csswg.org/selectors-3/#first-letter">Selectors Level 3<br />
<span class="small">The definition of '::first-letter' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Introduction of the two-colon syntax. Definition of edge-case behavior, such as in list items or with specific languages (e.g., the Dutch digraph <code>IJ</code>).</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/CSS2/selector.html#first-letter">CSS Level 2 (Revision 1)<br />
<span class="small">The definition of '::first-letter' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>No change.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/CSS1/#the-first-letter-pseudo-element">CSS Level 1<br />
<span class="small">The definition of '::first-letter' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition, using the one-colon syntax.</td></tr></tbody></table>

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

`::first-letter`

1

1

12

12

1

1

9

5.5

7

3.5

1

1

37

37

18

18

4

4

10.1

10.1

1

1

1.0

1.0

`dutch_ij_digraph`

No

No

87

No

No

No

No

No

87

No

No

No

## See also

- [`::first-line`](::first-line)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/::first-letter" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/::first-letter</a>
