# list-style-type

The `list-style-type` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets the marker (such as a disc, character, or custom counter style) of a list item element.

The [color](color_value) of the marker will be the same as the computed color of the element it applies to.

Only a few elements ([`<li>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/li) and [`<summary>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/summary)) have a default value of `display: list-item`. However, the `list-style-type` property may be applied to any element whose [`display`](display) value is set to `list-item`. Moreover, because this property is inherited, it can be set on a parent element (commonly [`<ol>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/ol) or [`<ul>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/ul)) to make it apply to all list items.

## Syntax

    /* Partial list of types */
    list-style-type: disc;
    list-style-type: circle;
    list-style-type: square;
    list-style-type: decimal;
    list-style-type: georgian;
    list-style-type: trad-chinese-informal;
    list-style-type: kannada;

    /* <string> value */
    list-style-type: '-';

    /* Identifier matching an @counter-style rule */
    list-style-type: custom-counter-style;

    /* Keyword value */
    list-style-type: none;

    /* Global values */
    list-style-type: inherit;
    list-style-type: initial;
    list-style-type: unset;

The list-style-type property may be defined as any one of:

- a `<custom-ident>` value
- a `symbols()` value
- a `<string>` value
- the keyword `none`.

Note that:

- Some types require a suitable font installed to display as expected.
- The `cjk-ideographic` is identical to `trad-chinese-informal`; it exists for legacy reasons.

### Values

[`<custom-ident>`](custom-ident)  
A identifier matching the value of a [`@counter-style`](@counter-style) or one of the predefined styles:

[`symbols()`](<symbols()>)  
Defines an anonymous style of the list.

[`<string>`](string)  
The specified string will be used as the item's marker.

`none`  
No item marker is shown.

`disc`

- A filled circle (default value)

`circle`

- A hollow circle

`square`

- A filled square

`decimal`

- Decimal numbers
- Beginning with 1

`cjk-decimal` <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>

- Han decimal numbers
- E.g. 一, 二, 三, ..., 九八, 九九, 一〇〇

`decimal-leading-zero`

- Decimal numbers
- Padded by initial zeros
- E.g. 01, 02, 03, … 98, 99

`lower-roman`

- Lowercase roman numerals
- E.g. i, ii, iii, iv, v…

`upper-roman`

- Uppercase roman numerals
- E.g. I, II, III, IV, V…

`lower-greek`

- Lowercase classical Greek
- alpha, beta, gamma…
- E.g. α, β, γ…

`lower-alpha`  
`lower-latin`

- Lowercase ASCII letters
- E.g. a, b, c, … z
- `lower-latin` is unsupported in IE7 and earlier
- See [Browser compatibility](#browser_compatibility) section.

`upper-alpha`  
`upper-latin`

- Uppercase ASCII letters
- E.g. A, B, C, … Z
- `upper-latin` is unsupported in IE7 and earlier

`arabic-indic`  
`-moz-arabic-indic`

- E.g. ١, ٢, ٣, ٤, ٥, ٦

`armenian`

- Traditional Armenian numbering
- (ayb/ayp, ben/pen, gim/keem…

`bengali`  
`-moz-bengali`

- Example

`cambodian` <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>\*

- Example
- Is a synonym for `khmer`

`cjk-earthly-branch`  
`-moz-cjk-earthly-branch`

- Example

`cjk-heavenly-stem`  
`-moz-cjk-heavenly-stem`

- Example

`cjk-ideographic`<span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>

- Identical to `trad-chinese-informal`
- E.g. 一萬一千一百一十一

`devanagari`  
`-moz-devanagari`

- Example

`ethiopic-numeric` <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>

- Example

`georgian`

- Traditional Georgian numbering
- E.g. an, ban, gan, … he, tan, in…

`gujarati`  
`-moz-gujarati`

- Example

`gurmukhi`  
`-moz-gurmukhi`

- Example

`hebrew` <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>

- Traditional Hebrew numbering

`hiragana` <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>

- E.g. あ, い, う, え, お, か, き…
- (Japanese)

`hiragana-iroha` <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>

- E.g. い, ろ, は, に, ほ, へ, と…
- [Iroha](https://en.wikipedia.org/wiki/Iroha) is the old japanese ordering of syllabs.

`japanese-formal` <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>

- Japanese formal numbering to be used in legal or financial document.
- E.g., 壱萬壱阡壱百壱拾壱
- The kanjis are designed so that they can't be modified to look like another correct one

`japanese-informal` <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>

- Japanese informal numbering

`kannada`  
`-moz-kannada`

- Example

`katakana` <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>

- E.g. ア, イ, ウ, エ, オ, カ, キ…
- (Japanese)

`katakana-iroha` <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>

- E.g. イ, ロ, ハ, ニ, ホ, ヘ, ト…
- [Iroha](https://en.wikipedia.org/wiki/Iroha) is the old japanese ordering of syllabs.

`khmer`  
`-moz-khmer`

- Example

`korean-hangul-formal` <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>

- Korean hangul numbering.
- E.g., 일만 일천일백일십일

`korean-hanja-formal` <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>

- Formal Korean Han numbering.
- E.g. 壹萬 壹仟壹百壹拾壹

`korean-hanja-informal` <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>

- Korean hanja numbering.
- E.g., 萬 一千百十一

`lao`  
`-moz-lao`

- Example

`lower-armenian` <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>\*

- Example

`malayalam`  
`-moz-malayalam`

- Example

`mongolian` <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>

- Example

`myanmar`  
`-moz-myanmar`

- Example

`oriya`  
`-moz-oriya`

- Example

`persian` <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
`-moz-persian`

- E.g. ۱, ۲, ۳, ۴, ۵, ۶

`simp-chinese-formal` <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>

- Simplified Chinese formal numbering.
- E.g. 壹万壹仟壹佰壹拾壹

`simp-chinese-informal` <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>

- Simplified Chinese informal numbering.
- E.g. 一万一千一百一十一

`tamil` <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
`-moz-tamil`

- Example

`telugu`  
`-moz-telugu`

- Example

`thai`  
`-moz-thai`

- Example

`tibetan` <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>\*

- Example

`trad-chinese-formal` <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>

- Traditional Chinese formal numbering.
- E.g. 壹萬壹仟壹佰壹拾壹

`trad-chinese-informal` <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>

- Traditional Chinese informal numbering.
- E.g. 一萬一千一百一十一

`upper-armenian` <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>\*

- Example

`disclosure-open` <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>

- Symbol indicating that a disclosure widget such as [`<details>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/details) is opened.

`disclosure-closed` <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>

- Symbol indicating that a disclosure widget, like [`<details>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/details) is closed.

### Non-standard extensions

A few more predefined types are provided by Mozilla (Firefox), Blink (Chrome and Opera) and WebKit (Safari) to support list types in other languages. See the compatibility table to check which browsers supports which extension.

`-moz-ethiopic-halehame`

- Example

`-moz-ethiopic-halehame-am`

- Example

`ethiopic-halehame-ti-er`  
`-moz-ethiopic-halehame-ti-er`

- Example

`ethiopic-halehame-ti-et`  
`-moz-ethiopic-halehame-ti-et`

- Example

`hangul`  
`-moz-hangul`

- Example
- Example
- Example

`hangul-consonant`  
`-moz-hangul-consonant`

- Example
- Example
- Example

`urdu`  
`-moz-urdu`

- Example

## Accessibility concerns

The [VoiceOver](https://help.apple.com/voiceover/info/guide/) screen reader has an issue where unordered lists with a `list-style-type` value of `none` applied to them will not be announced as a list. To address this, add a [zero-width space](https://en.wikipedia.org/wiki/Zero-width_space) as [pseudo content](content) before each list item to ensure the list is announced properly. This ensures the design is unaffected by the bug fix and that list items are not improperly described.

    ul {
      list-style: none;
    }

    ul li::before {
      content: "\200B";
    }

- [VoiceOver and list-style-type: none – Unfettered Thoughts](https://unfetteredthoughts.net/2017/09/26/voiceover-and-list-style-type-none/)
- [MDN Understanding WCAG, Guideline 1.3 explanations](https://developer.mozilla.org/en-US/docs/Web/Accessibility/Understanding_WCAG/Perceivable#guideline_1.3_%e2%80%94_create_content_that_can_be_presented_in_different_ways)
- [Understanding Success Criterion 1.3.1 | W3C Understanding WCAG 2.0](https://www.w3.org/TR/UNDERSTANDING-WCAG20/content-structure-separation-programmatic.html)

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>disc</code></td></tr><tr class="even"><td>Applies to</td><td>list items</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>yes</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    <counter-style> | <string> | nonewhere
    <counter-style> = <counter-style-name> | symbols()where
    <counter-style-name> = <custom-ident>

## Examples

### Setting list item markers

#### HTML

    List 1
    <ol class="normal">
      <li>Hello</li>
      <li>World</li>
      <li>What's up?</li>
    </ol>

    List 2
    <ol class="shortcut">
      <li>Looks</li>
      <li>Like</li>
      <li>The</li>
      <li>Same</li>
    </ol>

#### CSS

    ol.normal {
      list-style-type: upper-alpha;
    }

    /* or use the shortcut "list-style": */
    ol.shortcut {
      list-style: upper-alpha;
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-counter-styles-3/#extending-css2">CSS Counter Styles Level 3<br />
<span class="small">The definition of 'list-style-type' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Redefines CSS2.1 counters.<br />
Extends the syntax to support <code>@counter-style</code> rules.<br />
Defines using <code>@counter-style</code> the usual style types: <code>hebrew</code>, <code>cjk-ideographic</code>, <code>hiragana</code>, <code>hiragana-iroha</code>, <code>katakana</code>, <code>katakana-iroha</code>, <code>japanese-formal</code>, <code>japanese-informal</code>, <code>simp-chinese-formal</code>, <code>trad-chinese-formal</code>, <code>simp-chinese-formal</code>, <code>trad-chinese-formal</code>,<code>korean-hangul-formal</code>, <code>korean-hanja-informal</code>, <code>korean-hanja-formal</code>, <code>cjk-decimal</code>, <code>ethiopic-numeric</code>, <code>disclosure-open</code> and <code>disclosure-closed</code>.<br />
Extends <code>&lt;counter-style&gt;</code> with the <code>symbols()</code> functional notation.</td></tr><tr class="even"><td><a href="https://drafts.csswg.org/css-lists-3/#propdef-list-style-type">CSS Lists Module Level 3<br />
<span class="small">The definition of 'list-style-type' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Modify syntax to support for identifiers used in <code>@counter-style</code> rules to keywords.<br />
Support for a simple <code>&lt;string&gt;</code>.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/CSS2/generate.html#propdef-list-style-type">CSS Level 2 (Revision 1)<br />
<span class="small">The definition of 'list-style-type' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`list-style-type`

1

12

1

4

3.5

1

1

18

4

10.1

1

1.0

`afar`

6-45

No

No

No

15-32

5

3-45

18-45

No

14-32

4.2

1.0-5.0

`amharic`

6-45

No

No

No

15-32

5

3-45

18-45

No

14-32

4.2

1.0-5.0

`amharic-abegede`

6-45

No

No

No

15-32

5

3-45

18-45

No

14-32

4.2

1.0-5.0

`arabic-indic`

6

79

33

1

No

15

5

1

18

33

4

14

4.2

1.0

`armenian`

1

12

1

8

6

1

1

18

4

10.1

1

1.0

`asterisks`

13-45

No

No

No

15-32

5.1

4.4-45

18-45

No

14-32

5

1.0-5.0

`bengali`

6

79

33

1

No

15

5

1

18

33

4

14

4.2

1.0

`binary`

13-45

No

No

No

15-32

5

4.4-45

18-45

No

14-32

4.2

1.0-5.0

`cambodian`

6

79

33

No

15

5

1

18

33

14

4.2

1.0

`circle`

1

12

1

4

3.5

1

1

18

4

10.1

1

1.0

`cjk-decimal`

No

No

28

No

No

No

No

No

28

No

No

No

`cjk-earthly-branch`

6

79

33

1

No

15

5

1

18

33

4

14

4.2

1.0

`cjk-heavenly-stem`

6

79

33

1

No

15

5

1

18

33

4

14

4.2

1.0

`cjk-ideographic`

1

79

1

No

15

7

Until version 15, only decimal numbers display.

5

1

18

4

14

10.1

Until version 15, only decimal numbers display.

4.2

1.0

`decimal`

1

12

1

4

3.5

1

1

18

4

10.1

1

1.0

`decimal-leading-zero`

1

12

1

8

8

1

1

18

4

10.1

1

1.0

`devanagari`

6

79

33

1

No

15

5

1

18

33

4

14

4.2

1.0

`disc`

1

12

1

4

3.5

1

1

18

4

10.1

1

1.0

`disclosure-closed`

No

No

33

No

No

No

No

No

33

No

No

No

`disclosure-open`

No

No

33

No

No

No

No

No

33

No

No

No

`ethiopic`

6-45

No

No

No

15-32

5

3-45

18-45

No

14-32

4.2

1.0-5.0

`ethiopic-abegede`

6-45

No

No

No

15-32

5

3-45

18-45

No

14-32

4.2

1.0-5.0

`ethiopic-abegede-am-et`

6-45

No

No

No

15-32

5

3-45

18-45

No

14-32

4.2

1.0-5.0

`ethiopic-abegede-gez`

6-45

No

No

No

15-32

5

3-45

18-45

No

14-32

4.2

1.0-5.0

`ethiopic-abegede-ti-er`

6-45

No

No

No

15-32

5

3-45

18-45

No

14-32

4.2

1.0-5.0

`ethiopic-abegede-ti-et`

6-45

No

No

No

15-32

5

3-45

18-45

No

14-32

4.2

1.0-5.0

`ethiopic-halehame`

45

79

1

No

32

No

45

45

4

32

No

5.0

`ethiopic-halehame-aa-er`

6-45

No

No

No

15-32

5

3-45

18-45

No

14-32

4.2

1.0-5.0

`ethiopic-halehame-aa-et`

6-45

No

No

No

15-32

5

3-45

18-45

No

14-32

4.2

1.0-5.0

`ethiopic-halehame-am`

45

79

1

No

32

5

45

45

4

32

4.2

5.0

`ethiopic-halehame-am-et`

6-45

No

No

No

15-32

5

3-45

18-45

No

14-32

4.2

1.0-5.0

`ethiopic-halehame-gez`

6-45

No

No

No

15-32

5

3-45

18-45

No

14-32

4.2

1.0-5.0

`ethiopic-halehame-om-et`

6-45

No

No

No

15-32

5

3-45

18-45

No

14-32

4.2

1.0-5.0

`ethiopic-halehame-sid-et`

6-45

No

No

No

15-32

5

3-45

18-45

No

14-32

4.2

1.0-5.0

`ethiopic-halehame-so-et`

6-45

No

No

No

15-32

5

3-45

18-45

No

14-32

4.2

1.0-5.0

`ethiopic-halehame-ti-er`

6

79

1

No

15

5

3

18

4

14

4.2

1.0

`ethiopic-halehame-ti-et`

6

79

1

No

15

5

3

18

4

14

4.2

1.0

`ethiopic-halehame-tig`

6-45

No

No

No

15-32

5

3-45

18-45

No

14-32

4.2

1.0-5.0

`ethiopic-numeric`

No

No

33

Before Firefox 38, Firefox added a dot as suffix of the number for `ethiopic-numeric` (for example, ፫. instead of ፫). The specification later defined the absence of a suffix, which Firefox 38 followed.

1

No

No

No

No

No

33

Before Firefox 38, Firefox added a dot as suffix of the number for `ethiopic-numeric` (for example, ፫. instead of ፫). The specification later defined the absence of a suffix, which Firefox 38 followed.

4

No

No

No

`footnotes`

13-45

No

No

No

15-32

5.1

4.4-45

18-45

No

14-32

5

1.0-5.0

`georgian`

1

12

1

8

6

1

1

18

4

10.1

1

1.0

`gujarati`

6

79

33

1

No

15

5

1

18

33

4

14

4.2

1.0

`gurmukhi`

6

79

33

1

No

15

5

1

18

33

4

14

4.2

1.0

`hangul`

6

79

1

No

15

5

1

18

4

14

4.2

1.0

`hangul-consonant`

6

79

1

No

15

5

1

18

4

14

4.2

1.0

`hebrew`

1

79

1

No

15

1

1

18

4

14

1

1.0

`hiragana`

1

79

1

No

15

1

1

18

4

14

1

1.0

`hiragana-iroha`

1

79

1

No

15

1

1

18

4

14

1

1.0

`japanese-formal`

No

No

28

1

No

No

No

No

No

28

4

No

No

No

`japanese-informal`

No

No

28

1

No

No

No

No

No

28

4

No

No

No

`kannada`

6

79

33

1

No

15

5

1

18

33

4

14

4.2

1.0

`katakana`

1

79

1

No

15

1

1

18

4

14

1

1.0

`katakana-iroha`

1

79

1

No

15

1

1

18

4

14

1

1.0

`khmer`

6

79

33

1

No

15

5

1

18

33

4

14

4.2

1.0

`korean-hangul-formal`

45

79

28

No

32

No

45

45

28

32

No

5.0

`korean-hanja-formal`

45

79

28

No

32

No

45

45

28

32

No

5.0

`korean-hanja-informal`

45

79

28

No

32

No

45

45

28

32

No

5.0

`lao`

6

79

33

1

No

15

5

1

18

33

4

14

4.2

1.0

`lower-alpha`

1

12

1

8

6

1

1

18

4

10.1

1

1.0

`lower-armenian`

13

79

33

No

15

5.1

1

18

33

14

5

1.0

`lower-greek`

1

12

1

8

6

1

1

18

4

10.1

1

1.0

`lower-hexadecimal`

6-45

No

No

No

15-32

5

3-45

18-45

No

14-32

4.2

1.0-5.0

`lower-latin`

1

12

1

8

6

1

1

18

4

10.1

1

5.0

`lower-norwegian`

6-45

No

No

No

15-32

5

3-45

18-45

No

14-32

4.2

1.0-5.0

`lower-roman`

1

12

1

8

6

1

1

18

4

10.1

1

1.0

`malayalam`

6

79

33

1

No

15

5

1

18

33

4

14

4.2

1.0

`mongolian`

6

79

33

No

15

5

1

18

33

14

4.2

1.0

`myanmar`

6

79

33

1

No

15

5

1

18

33

4

14

4.2

1.0

`octal`

6-45

No

No

No

15-32

5

1-45

18-45

No

14-32

4.2

1.0-5.0

`oriya`

6

79

33

1

No

15

5

1

18

33

4

14

4.2

1.0

`oromo`

6-45

No

No

No

15-32

5

1-45

18-45

No

14-32

4.2

1.0-5.0

`persian`

6

79

33

1

No

15

5

1

18

33

4

14

4.2

1.0

`sidama`

6-45

No

No

No

15-32

5

1-45

18-45

No

14-32

4.2

1.0-5.0

`simp-chinese-formal`

45

79

28

1

No

32

No

45

45

28

4

32

No

5.0

`simp-chinese-informal`

45

79

28

1

No

32

No

45

45

28

4

32

No

5.0

`somali`

6-45

No

No

No

15-32

5

1-45

18-45

No

14-32

4.2

1.0-5.0

`square`

1

12

1

4

3.5

1

1

18

4

10.1

1

1.0

`string`

79

79

39

No

66

No

79

79

39

No

No

12.0

`symbols`

No

No

35

No

No

No

No

No

35

No

No

No

`tamil`

No

No

33

1

No

No

No

No

No

33

4

No

No

No

`telugu`

6

79

33

1

No

15

5

1

18

33

4

14

4.2

1.0

`thai`

6

79

33

1

No

15

5

1

18

33

4

14

4.2

1.0

`tibetan`

6

79

33

No

15

5

1

18

No

14

4.2

1.0

`tigre`

6-45

No

No

No

15-32

5

1-45

18-45

No

14-32

4.2

1.0-5.0

`tigrinya-er`

6-45

No

No

No

15-32

5

1-45

18-45

No

14-32

4.2

1.0-5.0

`tigrinya-er-abegede`

6-45

No

No

No

15-32

5

1-45

18-45

No

14-32

4.2

1.0-5.0

`tigrinya-et`

6-45

No

No

No

15-32

5

1-45

18-45

No

14-32

4.2

1.0-5.0

`tigrinya-et-abegede`

6-45

No

No

No

15-32

5

1-45

18-45

No

14-32

4.2

1.0-5.0

`trad-chinese-formal`

45

79

28

1

No

32

No

45

45

28

4

32

No

5.0

`trad-chinese-informal`

45

79

28

1

No

32

No

45

45

28

4

32

No

5.0

`upper-alpha`

1

12

1

8

6

1

1

18

4

10.1

1

1.0

`upper-armenian`

13

79

33

No

15

5.1

1

18

33

14

5

1.0

`upper-greek`

1

12

1

8

6

1

1

18

4

10.1

1

1.0

`upper-hexadecimal`

6-45

No

No

No

15-32

5

3-45

18-45

No

14-32

4.2

1.0-5.0

`upper-latin`

1

12

1

8

6

1

1

18

4

10.1

1

1.0

`upper-norwegian`

6-45

No

No

No

15-32

5

3-45

18-45

No

14-32

4.2

1.0-5.0

`upper-roman`

1

12

1

8

6

1

1

18

4

10.1

1

1.0

`urdu`

6

79

33

No

15

5

1

18

33

14

4.2

1.0

## See also

- [`list-style`](list-style), [`list-style-image`](list-style-image), [`list-style-position`](list-style-position)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/list-style-type" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/list-style-type</a>
