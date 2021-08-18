# word-break

The `word-break` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets whether line breaks appear wherever the text would otherwise overflow its content box.

## Syntax

    /* Keyword values */
    word-break: normal;
    word-break: break-all;
    word-break: keep-all;
    word-break: break-word; /* deprecated */

    /* Global values */
    word-break: inherit;
    word-break: initial;
    word-break: unset;

The `word-break` property is specified as a single keyword chosen from the list of values below.

### Values

`normal`  
Use the default line break rule.

`break-all`  
To prevent overflow, word breaks should be inserted between any two characters (excluding Chinese/Japanese/Korean text).

`keep-all`  
Word breaks should not be used for Chinese/Japanese/Korean (CJK) text. Non-CJK text behavior is the same as for `normal`.

`break-word` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Has the same effect as `word-break: normal` and `overflow-wrap: anywhere`, regardless of the actual value of the [`overflow-wrap`](overflow-wrap) property.

**Note:** In contrast to `word-break: break-word` and `overflow-wrap: break-word` (see [`overflow-wrap`](overflow-wrap)), `word-break: break-all` will create a break at the exact place where text would otherwise overflow its container (even if putting an entire word on its own line would negate the need for a break).

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>normal</code></td></tr><tr class="even"><td>Applies to</td><td>all elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>yes</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    normal | break-all | keep-all | break-word

## Examples

### HTML

    <p>1. <code>word-break: normal</code></p>
    <p class="normal narrow">This is a long and
     Honorificabilitudinitatibus califragilisticexpialidocious Taumatawhakatangihangakoauauotamateaturipukakapikimaungahoronukupokaiwhenuakitanatahu
     グレートブリテンおよび北アイルランド連合王国という言葉は本当に長い言葉</p>

    <p>2. <code>word-break: break-all</code></p>
    <p class="breakAll narrow">This is a long and
     Honorificabilitudinitatibus califragilisticexpialidocious Taumatawhakatangihangakoauauotamateaturipukakapikimaungahoronukupokaiwhenuakitanatahu
     グレートブリテンおよび北アイルランド連合王国という言葉は本当に長い言葉</p>

    <p>3. <code>word-break: keep-all</code></p>
    <p class="keepAll narrow">This is a long and
     Honorificabilitudinitatibus califragilisticexpialidocious Taumatawhakatangihangakoauauotamateaturipukakapikimaungahoronukupokaiwhenuakitanatahu
     グレートブリテンおよび北アイルランド連合王国という言葉は本当に長い言葉</p>

    <p>4. <code>word-break: break-word</code></p>
    <p class="breakWord narrow">This is a long and
      Honorificabilitudinitatibus califragilisticexpialidocious Taumatawhakatangihangakoauauotamateaturipukakapikimaungahoronukupokaiwhenuakitanatahu
     グレートブリテンおよび北アイルランド連合王国という言葉は本当に長い言葉</p>

### CSS

    .narrow {
      padding: 10px;
      border: 1px solid;
      width: 500px;
      margin: 0 auto;
      font-size: 20px;
      line-height: 1.5;
      letter-spacing: 1px;
    }

    .normal {
      word-break: normal;
    }

    .breakAll {
      word-break: break-all;
    }

    .keepAll {
      word-break: keep-all;
    }

    .breakWord {
      word-break: break-word;
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-text-3/#word-break-property">CSS Text Module Level 3<br />
<span class="small">The definition of 'word-break' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`word-break`

1

12

15

5.5

No version of Internet Explorer supports the `initial` value.

8

Don't use `-ms-word-break`, which is a synonym for `word-break`.

15

3

≤37

18

15

14

2

1.0

`break-word`

1

79

67

No

15

3

≤37

18

67

14

2

1.0

`keep-all`

44

12

15

5.5

31

9

44

44

15

32

9

4.0

## See also

- [`overflow-wrap`](overflow-wrap)
- [`hyphens`](hyphens)
- [Guide to wrapping and breaking text](css_text/wrapping_text)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/word-break" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/word-break</a>
