# orphans

The `orphans` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets the minimum number of lines in a block container that must be shown at the _bottom_ of a [page](https://developer.mozilla.org/en-US/docs/Web/CSS/Paged_Media), region, or [column](css_columns).

    /* <integer> values */
    orphans: 2;
    orphans: 3;

    /* Global values */
    orphans: inherit;
    orphans: initial;
    orphans: unset;

In typography, an _orphan_ is the first line of a paragraph that appears alone at the bottom of a page. (The paragraph continues on a following page.)

## Syntax

### Values

[`<integer>`](integer)  
The minimum number of lines that can stay by themselves at the bottom of a fragment before a fragmentation break. The value must be positive.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>2</code></td></tr><tr class="even"><td>Applies to</td><td>block container elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>yes</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    <integer>

## Examples

### Setting a minimum orphan size of three lines

#### HTML

    <div>
      <p>This is the first paragraph containing some text.</p>
      <p>This is the second paragraph containing some more text than the first one. It is used to demonstrate how orphans work.</p>
      <p>This is the third paragraph. It has a little bit more text than the first one.</p>
    </div>

#### CSS

    div {
      background-color: #8cffa0;
      height: 150px;
      columns: 3;
      orphans: 3;
    }

    p {
      background-color: #8ca0ff;
    }

    p:first-child {
      margin-top: 0;
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-break-3/#widows-orphans">CSS Fragmentation Module Level 3<br />
<span class="small">The definition of 'orphans' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Extends <code>orphans</code> to apply to any type of fragment, including pages, regions, or columns.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/CSS2/page.html#break-inside">CSS Level 2 (Revision 1)<br />
<span class="small">The definition of 'orphans' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`orphans`

25

12

No

8

9.2

1.3

≤37

25

No

14

1

1.5

## See also

- [`widows`](widows)
- [Paged media](https://developer.mozilla.org/en-US/docs/Web/CSS/Paged_Media)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/orphans" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/orphans</a>
