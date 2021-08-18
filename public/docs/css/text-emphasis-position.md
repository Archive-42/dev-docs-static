# text-emphasis-position

The `text-emphasis-position` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets where emphasis marks are drawn. Like ruby text, if there isn't enough room for emphasis marks, the line height is increased.

    /* Initial value */
    text-emphasis-position: over right;

    /* Keywords value */
    text-emphasis-position: over left;
    text-emphasis-position: under right;
    text-emphasis-position: under left;

    text-emphasis-position: left over;
    text-emphasis-position: right under;
    text-emphasis-position: left under;

    /* Global values */
    text-emphasis-position: inherit;
    text-emphasis-position: initial;
    text-emphasis-position: unset;

## Syntax

### Values

`over`  
Draw marks over the text in horizontal writing mode.

`under`  
Draw marks under the text in horizontal writing mode.

`right`  
Draws marks to the right of the text in vertical writing mode.

`left`  
Draw marks to the left of the text in vertical writing mode.

## Description

The preferred position of emphasis marks depends on the language. In Japanese for example, the preferred position is <span class="css">over right</span>. In Chinese, on the other hand, the preferred position is <span class="css">under right</span>. The informative table below summarizes the preferred emphasis mark positions for Chinese, Mongolian and Japanese:

Preferred emphasis mark and ruby position

Language

Preferred position

Illustration

Horizontal

Vertical

Japanese

over

right

<img src="data:image/png;base64,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" title="Emphasis (shown in blue for clarity) applied above a fragment of Japanese text" alt="Emphasis marks appear over each emphasized character in horizontal Japanese text." width="416" height="78" />

<img src="data:image/gif;base64,R0lGODlhIgBZAPECAAAAAAAA/wAAAAAAACH5BAUAAAIALAAAAAAiAFkAAAL/lI+py+0Po5xUAYCw0ObWnXDix3XZUUKY5pUsiYKbK09rOF86mdKfeQrCar1FwKFrzYC3ROCIzLxyKcGTccsyG9dFczqtfLc1ylgWtgFj6N/apHUXWVW1EOVx6/f8UL1fFmiWRJgEGJj2ULhY2Fckx2h4+McTKYkAJYbllOlnuajQdYjZaaGo97nzQ/kmlop6CvkJGzVqe4vEuqe76zWYSijn6zjMV8cr8QiobKTZalRaKwithmwVLX3bZDsy2mMdawEurpgXoaqCq75uro0jO7v8Dg7caPy++jo5WR+6ukkKS71LB0TdMmgqmyt9QxqM82SJlkNUDBsCXIcxI4UCADs=" title="Emphasis applied on the right of a fragment of Japanese text" alt="Emphasis marks appear on the right of each emphasized character in vertical Japanese text." width="34" height="89" />

Korean

Mongolian

Chinese

under

right

<img src="data:image/gif;base64,R0lGODlhhQAcAPECAAQEBAQE+gAAAAAAACH5BAUAAAIALAAAAACFABwAQAL/lI+py+0Po5wTJIuw0lzq9m3gtQDmiYVfKLCsCKLy7JbM22awfl8z/8BRhoxAYGgkKpdEYYsGdZqCDqGqeopEaSSgAdf55kZisnfcPYTVlnX5rd4x5/S6/Y7P6/eeNLxPFdgzGId2dlVo82fIuLL10+PEiGbl52O5AuP2h1hVYXm2yNRW1jkZJjkJkSrlmFUyFSpruvH4ykdxhITL2+v7CxwsPNyUyplI/JQhafwpuApqFvNIKIpCYexi62r7XC33tC3CwVUKtUgLlpjiyUz9LYUZWiMvS4k8wgwOP30IVH6q2zJxhFqJ23ZNDLtG896warLv2DdRl/CVqqdwi6poLN4mfnmR4tYmdYrwZYLWEeUNVrE2VmzpsRlFjslq2ryZJJeumzx7+vwJlGcBADs=" title="Emphasis (shown in blue for clarity) applied below a fragment of Chinese text" alt="Emphasis marks appear below each emphasized character in horizontal Simplified Chinese text." width="133" height="28" />

**Note**: The `text-emphasis-position` cannot be set, and therefore are not reset either, using the [`text-emphasis`](text-emphasis) shorthand property.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>over right</code></td></tr><tr class="even"><td>Applies to</td><td>all elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    [ over | under ] && [ right | left ]

## Examples

### Preferring ruby over emphasis marks

Some editors prefer to hide emphasis marks when they conflict with ruby. In HTML, this can be done with the following style rule:

    ruby {
      text-emphasis: none;
    }

### Preferring emphasis marks over ruby

Some other editors prefer to hide ruby when they conflict with emphasis marks. In HTML, this can be done with the following pattern:

    em {
      text-emphasis: dot; /* Set text-emphasis for <em> elements */
    }

    em rt {
      display: none; /* Hide ruby inside <em> elements */
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-text-decor-3/#text-emphasis-position-property">CSS Text Decoration Module Level 3<br />
<span class="small">The definition of 'text-emphasis' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`text-emphasis-position`

25

79

46

No

15

6.1

6.1

4.4

25

46

14

7

7

1.5

`left_and_right`

62

79

46

No

49

8

62

62

46

46

8

8.0

## See also

- The longhand properties [`text-emphasis-style`](text-emphasis-style), [`text-emphasis-color`](text-emphasis-color), and the corresponding shorthand property [`text-emphasis`](text-emphasis).

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/text-emphasis-position" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/text-emphasis-position</a>
