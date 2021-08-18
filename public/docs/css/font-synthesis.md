# font-synthesis

The `font-synthesis` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property controls which missing typefaces, bold or italic, may be synthesized by the browser.

## Syntax

This property can take any one of the following forms:

- The keyword value `none`.
- Either of the keyword values `weight` and `style`.
- Both the keyword values `weight` and `style`.

### Values

`none`  
Indicates that neither bold nor italic typeface may be synthesized.

`weight`  
Indicates that a bold typeface may be synthesized if needed.

`style`  
Indicates that an italic typeface may be synthesized if needed.

## Description

Most standard Western fonts include italic and bold variants, but many novelty fonts do not. Fonts used for Chinese, Japanese, Korean and other logographic scripts tend not to include these variants, and synthesizing them may impede the legibility of the text. In these cases, it may be desirable to switch off the browser's default font-synthesis.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>weight style</code></td></tr><tr class="even"><td>Applies to</td><td>all elements. It also applies to <a href="::first-letter"><code>::first-letter</code></a> and <a href="::first-line"><code>::first-line</code></a>.</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>yes</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    none | [ weight || style ]

## Examples

### Disabling font synthesis

#### HTML

    <em class="syn">Synthesize me! 站直。</em>
    <br/>
    <em class="no-syn">Don't synthesize me! 站直。</em>

#### CSS

    em {
      font-weight: bold;
    }
    .syn {
      font-synthesis: style weight;
    }
    .no-syn {
      font-synthesis: none;
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-fonts-3/#propdef-font-synthesis">CSS Fonts Module Level 3<br />
<span class="small">The definition of 'font-synthesis' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`font-synthesis`

No

No

34

No

No

9

No

No

34

No

9

No

## See also

- [`font-style`](font-style)
- [`font-weight`](font-weight)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/font-synthesis" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/font-synthesis</a>
