# hyphens

The `hyphens` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property specifies how words should be hyphenated when text wraps across multiple lines. It can prevent hyphenation entirely, hyphenate at manually-specified points within the text, or let the browser automatically insert hyphens where appropriate.

Hyphenation rules are language-specific. In HTML, the language is determined by the `lang` attribute, and browsers will hyphenate only if this attribute is present and the appropriate hyphenation dictionary is available. In XML, the `xml:lang` attribute must be used.

**Note:** The rules defining how hyphenation is performed are not explicitly defined by the specification, so the exact hyphenation may vary from browser to browser.

## Syntax

    /* Keyword values */
    hyphens: none;
    hyphens: manual;
    hyphens: auto;

    /* Global values */
    hyphens: inherit;
    hyphens: initial;
    hyphens: unset;

The `hyphens` property is specified as a single keyword value chosen from the list below.

### Values

`none`  
Words are not broken at line breaks, even if characters inside the words suggest line break points. Lines will only wrap at whitespace.

`manual`  
Words are broken for line-wrapping only where characters inside the word suggest line break opportunities. See [Suggesting line break opportunities](#suggesting_line_break_opportunities) below for details.

`auto`  
The browser is free to automatically break words at appropriate hyphenation points, following whatever rules it chooses. However, suggested line break opportunities (see [Suggesting line break opportunities](#suggesting_line_break_opportunities) below) will override automatic break point selection when present.

**Note:** The `auto` setting's behavior depends on the language being properly tagged to select the appropriate hyphenation rules. You must specify a language using the `lang` HTML attribute to guarantee that automatic hyphenation is applied in that language.

## Suggesting line break opportunities

There are two Unicode characters used to manually specify potential line break points within text:

U+2010 (HYPHEN)  
The "hard" hyphen character indicates a visible line break opportunity. Even if the line is not actually broken at that point, the hyphen is still rendered.

U+00AD (SHY)  
An invisible, "**s**oft" **hy**phen. This character is not rendered visibly; instead, it marks a place where the browser should break the word if hyphenation is necessary. In HTML, use `&shy;` to insert a soft hyphen.

When the HTML `<wbr>` element leads to a line break, no hyphen is added.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>manual</code></td></tr><tr class="even"><td>Applies to</td><td>all elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>yes</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    none | manual | auto

## Examples

### Specifying text hyphenation

This example uses three classes, one for each possible configuration of the `hyphens` property.

#### HTML

    <dl>
      <dt><code>none</code>: no hyphen; overflow if needed</dt>
      <dd lang="en" class="none">An extreme&shy;ly long English word</dd>
      <dt><code>manual</code>: hyphen only at &amp;hyphen; or &amp;shy; (if needed)</dt>
      <dd lang="en" class="manual">An extreme&shy;ly long English word</dd>
      <dt><code>auto</code>: hyphens where the algorithm decides (if needed)</dt>
      <dd lang="en" class="auto">An extreme&shy;ly long English word</dd>
    </dl>

#### CSS

    dd {
      width: 55px;
      border: 1px solid black;
     }
    dd.none {
      -webkit-hyphens: none;
      -ms-hyphens: none;
      hyphens: none;
    }
    dd.manual {
      -webkit-hyphens: manual;
      -ms-hyphens: manual;
      hyphens: manual;
    }
    dd.auto {
      -webkit-hyphens: auto;
      -ms-hyphens: auto;
      hyphens: auto;
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-text-3/#hyphens-property">CSS Text Module Level 3<br />
<span class="small">The definition of 'hyphens' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`hyphens`

55

`auto` value is only supported on macOS and Android and for languages the OS provides hyphenation for.

13

Only `-webkit-hyphens: none` is supported.

12

Only works if the specified language is the same as the language of the underlying OS.

43

6

Automatic hyphenation only works for languages with hyphenation dictionaries that are integrated into Firefox.

10

Only works if the specified language is the same as the language of the underlying OS.

44

`auto` value is only supported on macOS and Android.

5.1

55

4

55

18

43

6

Automatic hyphenation only works for languages with hyphenation dictionaries that are integrated into Firefox.

43

4.2

6.0

1.0

`afrikaans`

No

No

8

No

No

No

No

No

8

No

No

No

`bosnian`

No

No

8

No

No

No

No

No

8

No

No

No

`bulgarian`

No

No

8

No

No

No

No

No

8

No

No

No

`catalan`

No

No

8

No

No

5.1

No

No

8

No

5

No

`croatian`

No

No

8

No

No

9.1

No

No

8

No

9.3

No

`czech`

No

No

No

No

No

9.1

No

No

No

No

9.3

No

`danish`

No

No

8

No

No

5.1

No

No

8

No

5

No

`dutch`

No

No

8

No

No

5.1

No

No

8

No

5

No

`english`

55

12

6

For English, Firefox uses an en-US dictionary

10

44

5.1

For English, Safari uses different en-GB and en-US dictionaries.

55

55

6

For English, Firefox uses an en-US dictionary

43

6

For English, Safari uses different en-GB and en-US dictionaries.

6.0

`esperanto`

No

No

8

No

No

No

No

No

8

No

No

No

`estonian`

No

No

8

No

No

No

No

No

8

No

No

No

`finish`

No

No

8

No

No

9.1

No

No

8

No

9.3

No

`french`

No

No

8

No

No

5.1

No

No

8

No

5

No

`galician`

No

No

9

No

No

No

No

No

9

No

No

No

`german_reformed_orthography`

No

No

8

No

No

5.1

No

No

8

No

5

No

`german_swiss_orthography`

No

No

8

No

No

No

No

No

8

No

No

No

`german_traditional_orthography`

No

No

8

No

No

No

No

No

8

No

No

No

`hungarian`

No

No

9

No

No

9.1

No

No

9

No

9.3

No

`icelandic`

No

No

8

No

No

No

No

No

8

No

No

No

`interlingua`

No

No

8

No

No

No

No

No

8

No

No

No

`italian`

No

No

9

No

No

5.1

No

No

9

No

5

No

`kurmanji`

No

No

8

No

No

No

No

No

8

No

No

No

`latin`

No

No

8

No

No

No

No

No

8

No

No

No

`lithuanian`

No

No

8

No

No

No

No

No

8

No

No

No

`mongolian`

No

No

8

No

No

No

No

No

8

No

No

No

`norwegian_nn`

No

No

8

No

No

No

No

No

8

No

5

No

`norwegian_no`

No

No

8

No

No

5.1

No

No

8

No

5

No

`polish`

No

No

31

No

No

9.1

No

No

31

No

9.3

No

`portuguese`

No

No

8

No

No

9.1

No

No

8

No

9.3

No

`portuguese_brazillian`

No

No

8

For Brazilian Portuguese, Firefox uses a Portuguese dictionary.

No

No

No

No

No

8

For Brazilian Portuguese, Firefox uses a Portuguese dictionary.

No

No

No

`russian`

No

No

8

No

No

5.1

No

No

8

No

5

No

`slovenian`

No

No

8

No

No

No

No

No

8

No

No

No

`spanish`

No

No

8

No

No

5.1

No

No

8

No

5

No

`swedish`

No

No

8

No

No

5.1

No

No

8

No

5

No

`turkish`

No

No

9

No

No

5.1

No

No

9

No

5

No

`ukrainian`

No

No

9

No

No

9.1

No

No

9

No

9.3

No

`upper_sorbian`

No

No

8

No

No

No

No

No

8

No

No

No

`welsh`

No

No

8

No

No

No

No

No

8

No

No

No

## See also

- [`content`](content)
- [`overflow-wrap`](overflow-wrap) (formerly `word-wrap`)
- [`word-break`](word-break)
- [Guide to wrapping and breaking text](css_text/wrapping_text)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/hyphens" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/hyphens</a>
