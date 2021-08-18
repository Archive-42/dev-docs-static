# text-decoration-skip

The `text-decoration-skip` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets what parts of an element’s content any text decoration affecting the element must skip over. It controls all text decoration lines drawn by the element and also any text decoration lines drawn by its ancestors.

**Note:** Most other browsers are converging on supporting the simpler [`text-decoration-skip-ink`](text-decoration-skip-ink) property.

    /* Keyword values */
    text-decoration-skip: none;
    text-decoration-skip: objects;
    text-decoration-skip: spaces;
    text-decoration-skip: edges;
    text-decoration-skip: box-decoration;

    /* Multiple keywords */
    text-decoration-skip: objects spaces;
    text-decoration-skip: leading-spaces trailing-spaces;
    text-decoration-skip: objects edges box-decoration;

    /* Global values */
    text-decoration-skip: inherit;
    text-decoration-skip: initial;
    text-decoration-skip: unset;

## Syntax

### Values

`none`  
Nothing is skipped. Thus, text decoration is drawn for all text content and across atomic inline-level boxes.

`objects`  
The entire margin box of the element is skipped if it is an atomic inline such as an image or inline-block.

`spaces`  
All spacing is skipped: all [Unicode white space characters](https://www.unicode.org/reports/tr44/#White_Space) and all word separators, plus any adjacent [`letter-spacing`](letter-spacing) or [`word-spacing`](word-spacing).

`leading-spaces`  
The same as `spaces`, except that only leading spaces are skipped.

`trailing-spaces`  
The same as `spaces`, except that only trailing spaces are skipped.

`edges`  
The start and end of the text decoration is inset slightly (e.g., by half of the line thickness) from the content edge of the decorating box. Thus, adjacent elements receive separate underlines. (This is important in Chinese, where underlining is a form of punctuation.)

<img src="data:image/png;base64,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" alt="An example of &quot;text-decoration-skip: edges;&quot;." width="223" height="77" />

`box-decoration`  
The text decoration is skipped over the box's margin, border, and padding areas. This only has an effect on decorations imposed by an ancestor; a _decorating box_ never draws over its own box decoration.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>objects</code></td></tr><tr class="even"><td>Applies to</td><td>all elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>yes</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    none | [ objects || [ spaces | [ leading-spaces || trailing-spaces ] ] || edges || box-decoration ]

## Examples

### Skipping edges

#### HTML

    <p>Hey, grab a cup of <em>coffee!</em></p>

#### CSS

    p {
      margin: 0;
      font-size: 3em;
      text-decoration: underline;
      text-decoration-skip: edges;
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-text-decor-4/#text-decoration-skipping">CSS Text Decoration Module Level 4<br />
<span class="small">The definition of 'text-decoration-skip' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`text-decoration-skip`

57-64

Only supports the deprecated `ink` value.

No

No

No

44-50

Only supports the deprecated `ink` value.

12.1

Only supports the `none` and `skip` values; all other values behave like those two values.

8

Only supports the `none` and `skip` values; all other values behave like those two values.

57-64

Only supports the deprecated `ink` value.

57-64

Only supports the deprecated `ink` value.

No

43-46

Only supports the deprecated `ink` value.

12.2

Only supports the `none` and `skip` values; all other values behave like those two values.

8

Only supports the `none` and `skip` values; all other values behave like those two values.

7.0-9.0

Only supports the deprecated `ink` value.

## See also

- `text-decoration-skip-ink`

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/text-decoration-skip" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/text-decoration-skip</a>
