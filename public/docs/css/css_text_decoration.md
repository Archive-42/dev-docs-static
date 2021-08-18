# CSS Text Decoration

**CSS Text Decoration** is a module of CSS that defines features relating to text decoration, such as underlines, text shadows, and emphasis marks.

## Reference

### Properties

- [`letter-spacing`](letter-spacing)
- [`text-align`](text-align)
- [`text-decoration`](text-decoration)
- [`text-decoration-color`](text-decoration-color)
- [`text-decoration-line`](text-decoration-line)
- <span class="page-not-created">`text-decoration-offset`</span>
- [`text-decoration-skip-ink`](text-decoration-skip-ink)
- [`text-decoration-style`](text-decoration-style)
- [`text-decoration-thickness`](text-decoration-thickness)
- [`text-emphasis`](text-emphasis)
- [`text-emphasis-color`](text-emphasis-color)
- [`text-emphasis-position`](text-emphasis-position)
- [`text-emphasis-style`](text-emphasis-style)
- [`text-indent`](text-indent)
- [`text-rendering`](text-rendering)
- [`text-shadow`](text-shadow)
- [`text-transform`](text-transform)
- [`white-space`](white-space)
- [`word-spacing`](word-spacing)

## Guides

_None._

## Examples

    .under {
      text-decoration: underline red;
    }

    .over {
      text-decoration: wavy overline lime;
    }

    .line {
      text-decoration: line-through;
    }

    .plain {
      text-decoration: none;
    }

    .underover {
      text-decoration: dashed underline overline;
    }

    .thick {
      text-decoration: solid underline purple 4px;
    }

    .blink {
      text-decoration: blink;
    }

    <p class="under">This text has a line underneath it.</p>
    <p class="over">This text has a line over it.</p>
    <p class="line">This text has a line going through it.</p>
    <p>This <a class="plain" href="#">link will not be underlined</a>,
        as links generally are by default. Be careful when removing
        the text decoration on anchors since users often depend on
        the underline to denote hyperlinks.</p>
    <p class="underover">This text has lines above <em>and</em> below it.</p>
    <p class="thick">This text has a really thick purple underline in supporting browsers.</p>
    <p class="blink">This text might blink for you,
        depending on the browser you use.</p>

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-text-decor-4/">CSS Text Decoration Module Level 4</a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr><tr class="even"><td><a href="https://drafts.csswg.org/css-text-decor-3/">CSS Text Decoration Module Level 3</a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td></td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/CSS2/text.html">CSS Level 2 (Revision 1)</a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/CSS1/">CSS Level 1</a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Text_Decoration" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Text_Decoration</a>
