# initial-letter-align

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `initial-letter-align` CSS property specifies the alignment of initial letters within a paragraph.

    /* Keyword values */
    initial-letter-align: auto;
    initial-letter-align: alphabetic;
    initial-letter-align: hanging;
    initial-letter-align: ideographic;

    /* Global values */
    initial-letter-align: inherit;
    initial-letter-align: initial;
    initial-letter-align: unset;

## Syntax

One of the keyword values listed below.

### Values

`auto`  
The user agent selects the value which corresponds to the language of the text. Western languages would default to alphabetic, CJK languages to ideographic, and some Indic languages to hanging.

`alphabetic`  
As described above, the cap height of the initial letter aligns with the cap height of the first line of text. The baseline of the initial letter aligns with the baseline of the Nth text baseline.

`hanging`  
The hanging baseline of the initial letter aligns with the hanging baseline of the first line of text.

`ideographic`  
The initial letter is centered in the N-line area.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>auto</code></td></tr><tr class="even"><td>Applies to</td><td><a href="::first-letter"><code>::first-letter</code></a> pseudo-elements and inline-level first child of a block container</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    [ auto | alphabetic | hanging | ideographic ]

## Examples

### Aligning initial letter

#### HTML

    <p class="auto ">Initial letter - auto</p>
    <p class="alphabetic">Initial letter - alphabetic</p>
    <p class="hanging">Initial letter - hanging</p>
    <p class="ideographic">Initial letter - ideographic</p>

#### CSS

    .auto {
      -webkit-initial-letter-align: auto;
      initial-letter-align: auto;
    }

    .alphabetic {
      -webkit-initial-letter-align: alphabetic;
      initial-letter-align: alphabetic;
    }

    .hanging {
      -webkit-initial-letter-align: hanging;
      initial-letter-align: hanging;
    }

    .ideographic {
      -webkit-initial-letter-align: ideographic;
      initial-letter-align: ideographic;
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-inline/#aligning-initial-letter">CSS Inline Layout<br />
<span class="small">The definition of 'initial-letter-align' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`initial-letter-align`

No

No

No

See [bug 1273021](https://bugzil.la/1273021)

No

No

No

No

No

No

No

No

No

- [`initial-letter`](initial-letter)
- [Drop caps in CSS](https://www.oddbird.net/2017/01/03/initial-letter/)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/initial-letter-align" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/initial-letter-align</a>
