# text-decoration-skip-ink

The `text-decoration-skip-ink` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property specifies how overlines and underlines are drawn when they pass over glyph ascenders and descenders.

`text-decoration-skip-ink` is not part of the [`text-decoration`](text-decoration) shorthand.

## Syntax

    /* Single keyword */
    text-decoration-skip-ink: none;
    text-decoration-skip-ink: auto;
    text-decoration-skip-ink: all;

    /* Global keywords */
    text-decoration-skip: inherit;
    text-decoration-skip: initial;
    text-decoration-skip: unset;

### Values

`none`  
Underlines and overlines are drawn across the full length of the text content, including parts that cross over glyph descenders and ascenders.

`auto`  
The default — the browser _may_ interrupt underlines and overlines so that they do not touch or closely approach a glyph. That is, they are interrupted where they would otherwise cross over a glyph.

`all`  
The browser _must_ interrupt underlines and overlines so that they do not touch or closely approach a glyph. This can be helpful with certain Chinese, Japanese, or Korean (CJK) fonts, where the `auto` behavior might not create interruptions.

<img src="data:image/png;base64,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" alt="An example of &quot;text-decoration-skip-ink&quot;." width="223" height="77" />

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>auto</code></td></tr><tr class="even"><td>Applies to</td><td>all elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>yes</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    auto | all | none

## Examples

### HTML

    <p>You should go on a quest for a cup of coffee.</p>
    <p class="no-skip-ink">Or maybe you'd prefer some tea?</p>
    <p>この文は、 text-decoration-skip-ink: auto の使用例を示しています。</p>
    <p class="skip-ink-all">この文は、 text-decoration-skip-ink: all の使用例を示しています。</p>

### CSS

    p {
      font-size: 1.5em;
      text-decoration: underline blue;
      text-decoration-skip-ink: auto; /* this is the default anyway */
    }

    .no-skip-ink {
      text-decoration-skip-ink: none;
    }

    .skip-ink-all{
      text-decoration-skip-ink: all;
    }

### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-text-decor-4/#text-decoration-skip-ink-property">CSS Text Decoration Module Level 4<br />
<span class="small">The definition of 'text-decoration-skip-ink' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`text-decoration-skip-ink`

64

79

70

No

50

No

64

64

No

46

No

9.0

`all`

No

No

75

No

No

No

No

No

No

No

No

No

## See also

- [`text-decoration`](text-decoration)
- [`text-decoration-skip`](text-decoration-skip)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/text-decoration-skip-ink" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/text-decoration-skip-ink</a>
