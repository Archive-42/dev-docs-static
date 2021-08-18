# line-break

The `line-break` CSS property sets how to break lines of Chinese, Japanese, or Korean (CJK) text when working with punctuation and symbols.

    /* Keyword values */
    line-break: auto;
    line-break: loose;
    line-break: normal;
    line-break: strict;
    line-break: anywhere;

    /* Global values */
    line-break: inherit;
    line-break: initial;
    line-break: unset;

## Syntax

### Values

`auto`  
Break text using the default line break rule.

`loose`  
Break text using the least restrictive line break rule. Typically used for short lines, such as in newspapers.

`normal`  
Break text using the most common line break rule.

`strict`  
Break text using the most stringent line break rule.

`anywhere`  
There is a soft wrap opportunity around every typographic character unit, including around any punctuation character or preserved white spaces, or in the middle of words, disregarding any prohibition against line breaks, even those introduced by characters with the GL, WJ, or ZWJ character class or mandated by the [`word-break`](word-break) property. The different wrapping opportunities must not be prioritized. Hyphenation is not applied.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>auto</code></td></tr><tr class="even"><td>Applies to</td><td>all elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>yes</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    auto | loose | normal | strict | anywhere

## Examples

### Setting text wrapping

See whether the text is wrapped before "々", "ぁ" and "。".

#### HTML

    <div lang="ja">
      <p class="wrapbox auto">auto:<br>そこは湖のほとりで木々が輝いていた。<br>その景色に、美しいなぁと思わずつぶやいた。</p>
      <p class="wrapbox loose">loose:<br>そこは湖のほとりで木々が輝いていた。<br>その景色に、美しいなぁと思わずつぶやいた。</p>
      <p class="wrapbox normal">normal:<br>そこは湖のほとりで木々が輝いていた。<br>その景色に、美しいなぁと思わずつぶやいた。</p>
      <p class="wrapbox strict">strict:<br>そこは湖のほとりで木々が輝いていた。<br>その景色に、美しいなぁと思わずつぶやいた。</p>
      <p class="wrapbox anywhere">anywhere:<br>そこは湖のほとりで木々が輝いていた。<br>その景色に、美しいなぁと思わずつぶやいた。</p>
    </div>

#### CSS

    .wrapbox { width: 10em; margin: 0.5em; white-space: normal; vertical-align: top; display: inline-block; }
    .auto { line-break: auto; }
    .loose { line-break: loose; }
    .normal { line-break: normal; }
    .strict { line-break: strict; }
    .anywhere { line-break: anywhere; }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-text-3/#line-break-property">CSS Text Module Level 3<br />
<span class="small">The definition of 'line-break' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`line-break`

58

1

14

69

5.5

8

45

15

11

3

2-3

58

≤37

58

18

No

43

14

11

1

7.0

1.0

- [CSS and International text](https://www.w3.org/International/articles/css3-text/)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/line-break" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/line-break</a>
