# text-transform

The `text-transform` CSS property specifies how to capitalize an element's text. It can be used to make text appear in all-uppercase or all-lowercase, or with each word capitalized. It also can help improve legibility for ruby.

The `text-transform` property takes into account language-specific case mapping rules such as the following:

- In Turkic languages, like Turkish (`tr`), Azerbaijani (`az`), Crimean Tatar (`crh`), Volga Tatar (`tt`), and Bashkir (`ba`), there are two kinds of `i`, with and without the dot, and two case pairings: `i`/`İ` and `ı`/`I`.

- In German (`de`), the `ß` becomes `SS` in uppercase.

- In Dutch (`nl`), the `ij` digraph becomes `IJ`, even with `text-transform: capitalize`, which only puts the first letter of a word in uppercase.

- In Greek (`el`), vowels lose their accent when the whole word is in uppercase (`ά`/`Α`), except for the disjunctive eta (`ή`/`Ή`). Also, diphthongs with an accent on the first vowel lose the accent and gain a diaeresis on the second vowel (`άι`/`ΑΪ`).

- In Greek (`el`), the lowercase sigma character has two forms: `σ` and `ς`. `ς` is used only when sigma terminates a word. When applying `text-transform: lowercase` to an uppercase sigma (`Σ`), the browser needs to choose the right lowercase form based on context.

- in Irish (`ga`), certain prefixed letters remain in lowercase when the base initial is capitalized, so for example `text-transform: uppercase` will change `ar aon tslí` to `AR AON tSLÍ` and not, as one might expect, `AR AON TSLÍ` (Firefox only). In some cases, a hyphen is also removed upon uppercasing: `an t-uisce` transforms to `AN tUISCE` (and the hyphen is correctly reinserted by `text-transform: lowercase`).

The language is defined by the `lang` HTML attribute or the `xml:lang` XML attribute.

**Note:** Support for language-specific cases varies between browsers, so check the [browser compatibility table](#browser_compatibility).

## Syntax

    /* Keyword values */
    text-transform: none;
    text-transform: capitalize;
    text-transform: uppercase;
    text-transform: lowercase;
    text-transform: full-width;
    text-transform: full-size-kana;

    /* Global values */
    text-transform: inherit;
    text-transform: initial;
    text-transform: unset;

`capitalize`  
Is a keyword that converts the first _letter_ of each word to uppercase. Other characters remain unchanged (they retain their original case as written in the element's text). A letter is defined as a character that is part of Unicode's Letter or Number general categories <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>; thus, any punctuation marks or symbols at the beginning of a word are ignored.

Authors should not expect `capitalize` to follow language-specific title casing conventions (such as skipping articles in English).

The `capitalize` keyword was under-specified in CSS 1 and CSS 2.1. This resulted in differences between browsers in the way the first letter was calculated (Firefox considered `-` and `_` as letters, but other browsers did not. Both Webkit and Gecko incorrectly considered letter-based symbols like `ⓐ` to be real letters. Internet Explorer 9 was the closest to the CSS 2 definition, but with some weird cases.) By precisely defining the correct behavior, CSS Text Level 3 cleans this mess up. The `capitalize` line in the browser compatibility table contains the version the different engines started to support this now precisely-defined behavior.

`uppercase`  
Is a keyword that converts all characters to uppercase.

`lowercase`  
Is a keyword that converts all characters to lowercase.

`none`  
Is a keyword that prevents the case of all characters from being changed.

`full-width`  
Is a keyword that forces the writing of a character — mainly ideograms and Latin scripts — inside a square, allowing them to be aligned in the usual East Asian scripts (like Chinese or Japanese).

`full-size-kana`  
Generally used for [`<ruby>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/ruby) annotation text, the keyword converts all small Kana characters to the equivalent full-size Kana, to compensate for legibility issues at the small font sizes typically used in ruby.

## Accessibility concerns

Large sections of text set with a `text-transform` value of `uppercase` may be difficult for people with cognitive concerns such as Dyslexia to read.

- [MDN Understanding WCAG, Guideline 1.4 explanations](https://developer.mozilla.org/en-US/docs/Web/Accessibility/Understanding_WCAG/Perceivable#guideline_1.4_make_it_easier_for_users_to_see_and_hear_content_including_separating_foreground_from_background)
- [W3C Understanding WCAG 2.1](https://www.w3.org/TR/WCAG21/#visual-presentation)

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>none</code></td></tr><tr class="even"><td>Applies to</td><td>all elements. It also applies to <a href="::first-letter"><code>::first-letter</code></a> and <a href="::first-line"><code>::first-line</code></a>.</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>yes</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    none | capitalize | uppercase | lowercase | full-width | full-size-kana

## Examples

### `none`

    <p>Initial String
      <strong>Lorem ipsum dolor sit amet, consectetur adipisicing elit, ...</strong>
    </p>
    <p>text-transform: none
      <strong><span>Lorem ipsum dolor sit amet, consectetur adipisicing elit, ...</span></strong>
    </p>

    span {
      text-transform: none;
    }
    strong { float: right; }

This demonstrates no text transformation.

### capitalize (General)

    <p>Initial String
      <strong>Lorem ipsum dolor sit amet, consectetur adipisicing elit, ...</strong>
    </p>
    <p>text-transform: capitalize
      <strong><span>Lorem ipsum dolor sit amet, consectetur adipisicing elit, ...</span></strong>
    </p>

    span {
      text-transform: capitalize;
    }
    strong { float: right; }

This demonstrates text capitalization.

### capitalize (Punctuation)

    <p>Initial String
      <strong>(this) “is” [a] –short– -test- «for» *the* _css_ ¿capitalize? ?¡transform!</strong>
    </p>
    <p>text-transform: capitalize
      <strong><span>(this) “is” [a] –short– -test- «for» *the* _css_ ¿capitalize? ?¡transform!</span></strong>
    </p>

    span {
      text-transform: capitalize;
    }
    strong { float: right; }

This demonstrates how initial punctuations of a word are ignored. The keyword target the first letter, that is the first Unicode character part of the Letter or Number general category.

### capitalize (Symbols)

    <p>Initial String
      <strong>ⓐⓑⓒ (ⓓⓔⓕ) —ⓖⓗⓘ— ⓙkl</strong>
    </p>
    <p>text-transform: capitalize
      <strong><span>ⓐⓑⓒ (ⓓⓔⓕ) —ⓖⓗⓘ— ⓙkl</span></strong>
    </p>

    span {
      text-transform: capitalize;
    }
    strong { float: right; }

This demonstrates how initial symbols are ignored. The keyword target the first letter, that is the first Unicode character part of the Letter or Number general category.

### capitalize (Dutch ij digraph)

    <p>Initial String
      <strong lang="nl">The Dutch word: "ijsland" starts with a digraph.</strong>
    </p>
    <p>text-transform: capitalize
      <strong><span lang="nl">The Dutch word: "ijsland" starts with a digraph.</span></strong>
    </p>

    span {
      text-transform: capitalize;
    }
    strong { float: right; }

This demonstrates how the Dutch _ij_ digraph must be handled like one single letter.

### uppercase (General)

    <p>Initial String
      <strong>Lorem ipsum dolor sit amet, consectetur adipisicing elit, ...</strong>
    </p>
    <p>text-transform: uppercase
      <strong><span>Lorem ipsum dolor sit amet, consectetur adipisicing elit, ...</span></strong>
    </p>

    span {
      text-transform: uppercase;
    }
    strong { float: right; }

This demonstrates transforming the text to uppercase.

### uppercase (Greek Vowels)

    <p>Initial String
      <strong>Θα πάμε στο "Θεϊκό φαΐ" ή στη "Νεράιδα"</strong>
    </p>
    <p>text-transform: uppercase
      <strong><span lang="el">Θα πάμε στο "Θεϊκό φαΐ" ή στη "Νεράιδα"</span></strong>
    </p>

    span {
      text-transform: uppercase;
    }
    strong { float: right; }

This demonstrates how Greek vowels except disjunctive _eta_ should have no accent, and the accent on the first vowel of a vowel pair becomes a diaeresis on the second vowel.

### lowercase (General)

    <p>Initial String
      <strong>Lorem ipsum dolor sit amet, consectetur adipisicing elit, ...</strong>
    </p>
    <p>text-transform: lowercase
      <strong><span>Lorem ipsum dolor sit amet, consectetur adipisicing elit, ...</span></strong>
    </p>

    span {
      text-transform: lowercase;
    }
    strong { float: right; }

This demonstrates transforming the text to lowercase.

### lowercase (Greek Σ)

    <p>Initial String
      <strong>Σ IS A greek LETTER that appears SEVERAL TIMES IN ΟΔΥΣΣΕΥΣ.</strong>
    </p>
    <p>text-transform: lowercase
      <strong><span>Σ IS A greek LETTER that appears SEVERAL TIMES IN ΟΔΥΣΣΕΥΣ.</span></strong>
    </p>

    span {
      text-transform: lowercase;
    }
    strong { float: right; }

This demonstrates how the Greek character sigma (`Σ`) is transformed into the regular lowercase sigma (`σ`) or the word-final variant (`ς`), according the context.

### lowercase (Lithuanian)

    <p>Initial String
      <strong>Ĩ is a Lithuanian LETTER as is J́</strong>
    </p>
    <p>text-transform: lowercase
      <strong><span lang="lt">Ĩ is a Lithuanian LETTER as is J́</span></strong>
    </p>

    span {
      text-transform: lowercase;
    }
    strong { float: right; }

This demonstrates how the Lithuanian letters `Ĩ` and `J́` retain their dot when transformed to lowercase.

### full-width (General)

    <p>Initial String
      <strong>0123456789abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ!"#$%&()*+,-./:;<=>?@{|}~</strong>
    </p>
    <p>text-transform: full-width
      <strong><span>0123456789abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ!"#$%&()*+,-./:;<=>?@{|}~</span></strong>
    </p>

    span {
      text-transform: full-width;
    }
    strong { width: 100%; float: right; }

Some characters exists in two formats, normal width and a full-width, with different Unicode code points. The full-width version is used to mix them smoothly with Asian ideographic characters.

### full-width (Japanese half-width katakana)

    <p>Initial String
      <strong>ｳｪﾌﾞﾌﾟﾛｸﾞﾗﾐﾝｸﾞの勉強</strong>
    </p>
    <p>text-transform: full-width
      <strong><span>ｳｪﾌﾞﾌﾟﾛｸﾞﾗﾐﾝｸﾞの勉強</span></strong>
    </p>

    span {
      text-transform: full-width;
    }
    strong { width: 100%; float: right; }

The Japanese half-width katakana was used to represent katakana in 8-bit character codes. Unlike regular (full-width) katakana characters, a letter with dakuten (voiced sound mark) is represented as two code points, the body of letter and dakuten. The `full-width` combines these into a single code point when converting these characters into full-width.

### full-size-kana

    <p>ァィゥェ ォヵㇰヶ ㇱㇲッㇳ ㇴㇵㇶㇷ ㇸㇹㇺャ ュョㇻㇼ ㇽㇾㇿヮ</p>
    <p>ァィゥェ ォヵㇰヶ ㇱㇲッㇳ ㇴㇵㇶㇷ ㇸㇹㇺャ ュョㇻㇼ ㇽㇾㇿヮ</p>
    </p>

    p:nth-of-type(2) {
      text-transform: full-size-kana;
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-text-3/#text-transform">CSS Text Module Level 3<br />
<span class="small">The definition of 'text-transform' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>From <a href="https://www.w3.org/TR/CSS2/text.html#caps-prop">CSS Level 2 (Revision 1)<br />
<span class="small">The definition of 'text-transform' in that specification.</span></a>, extends letters to any Unicode character in the Number or Letter general category. Modifies the behavior of <code>capitalize</code> to apply to the first letter of the word, ignoring initial punctuations or symbols. Adds the <code>full-width</code> and <code>full-size-kana</code> keywords.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/CSS2/text.html#caps-prop">CSS Level 2 (Revision 1)<br />
<span class="small">The definition of 'text-transform' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>From <a href="https://www.w3.org/TR/CSS1/#text-transform">CSS Level 1<br />
<span class="small">The definition of 'text-transform' in that specification.</span></a>, extends letters to non-latin bi-cameral scripts</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/CSS1/#text-transform">CSS Level 1<br />
<span class="small">The definition of 'text-transform' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`text-transform`

1

The `text-transform` property does not work for `::first-line` pseudo-elements (nor for the one-colon syntax). See [Chromium bug 129669](https://crbug.com/129669).

12

1

4

7

Since Opera 15, the `text-transform` property does not work for `::first-line` pseudo-elements (nor for the one-colon syntax). See [Chromium bug 129669](https://crbug.com/129669).

1

The `text-transform` property does not work for `::first-line` pseudo-elements (also not for the old one-colon syntax). See [WebKit bug 3409](https://webkit.org/b/3409).

1

The `text-transform` property does not work for `::first-line` pseudo-elements (nor for the one-colon syntax). See [Chromium bug 129669](https://crbug.com/129669).

18

The `text-transform` property does not work for `::first-line` pseudo-elements (nor for the one-colon syntax). See [Chromium bug 129669](https://crbug.com/129669).

4

11

1

The `text-transform` property does not work for `::first-line` pseudo-elements (also not for the old one-colon syntax). See [WebKit bug 3409](https://webkit.org/b/3409).

1.0

The `text-transform` property does not work for `::first-line` pseudo-elements (nor for the one-colon syntax). See [Chromium bug 129669](https://crbug.com/129669).

`capitalize`

1

12

1

Before Firefox 14, some punctuation characters could interfere with correct capitalization. See [bug 731536](https://bugzil.la/731536).

4

7

1

1

18

4

Before Firefox 14, some punctuation characters could interfere with correct capitalization. See [bug 731536](https://bugzil.la/731536).

11

1

1.0

`dutch_ij_digraph`

No

No

14

No

No

No

No

No

14

No

No

No

`full-size-kana`

No

No

64

No

No

No

No

No

64

No

No

No

`full-width`

No

No

19

No

No

No

No

No

19

No

No

No

`greek_accented_characters`

34

79

15

No

21

No

4.4

34

15

21

No

2.0

`lowercase_sigma`

30

12

14

4

17

6

4.4

30

14

18

6

2.0

`turkic_is`

31

12

14

4

18

8

≤37

31

14

18

8

2.0

`uppercase_eszett`

1

18

1

No

7

1

1

18

4

11

1

1.0

## See also

- [`font-variant`](font-variant)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/text-transform" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/text-transform</a>
